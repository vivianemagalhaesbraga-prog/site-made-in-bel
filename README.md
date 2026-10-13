# Made in Bel Burguer: site de pedidos

Site de cardápio e pedidos da Made in Bel Burguer (Belford Roxo e Nova Iguaçu).
É um arquivo único (`index.html`), sem servidor e sem banco de dados.

## O que o site faz
- Cardápio por categorias, com busca, fotos e preços.
- Carrinho, adicionais, cupom (`PRIMEIROPEDIDO10`), entrega ou retirada e escolha da unidade.
- O pedido é montado em uma mensagem de WhatsApp. O cliente confere e envia por lá.
- Banner promocional com botão de copiar o cupom.
- Vídeos no topo e na seção "O sabor que fala por si".

## O que o site NÃO faz
- Não tem painel administrativo nem login: para mudar produtos ou preços, edite o `index.html`.
- Não registra pedidos em banco de dados e não processa pagamento online.
- Os pedidos só valem quando a loja responde no WhatsApp.

## Como editar os dados da loja
Abra o `index.html` em um editor de texto e procure por `CONFIGURAÇÃO` (perto do início do `<script>` principal).

| O que mudar | Onde |
|---|---|
| WhatsApp, horário, taxa de entrega, formas de pagamento | `CONFIG` |
| Unidades (nome, WhatsApp de cada uma, link do app, pedido mínimo) | `CONFIG.unidades` |
| Cupons | `CONFIG.cupons` |
| Adicionais que aparecem dentro de cada produto | `CONFIG.adicionais` |
| Ordem e nomes das abas | `CATS` |
| Produtos, descrições e preços | lista `P` (uma linha por produto) |

Cada linha de `P` segue esta ordem:
`["id", "categoria(s)", "Nome", "Descrição", preço, preço antigo, "etiqueta", "a partir de"]`.
Use `null` no preço para mostrar "Preço a confirmar".

Ainda faltam, para completar: endereço e telefone de cada unidade, e o WhatsApp de cada uma
(hoje as duas usam o mesmo número).

## Como publicar (GitHub Pages)
1. Envie estes arquivos para um repositório no GitHub.
2. No repositório: **Settings > Pages**.
3. Em **Build and deployment**, escolha **Deploy from a branch**, branch **main**, pasta **/ (root)**, e salve.
4. Em alguns minutos o site fica em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

## Observações
- As fontes (Google Fonts) precisam de internet para carregar.
- Os vídeos são carregados por JavaScript. Visualizadores de arquivo que bloqueiam JavaScript mostram uma versão simplificada do cardápio.
- No celular, alguns navegadores bloqueiam o início automático do vídeo. Nesse caso aparece um botão de play.
