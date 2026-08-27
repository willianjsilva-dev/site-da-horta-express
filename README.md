# 🥬 Da Horta Express

Site de vendas de frutas, verduras e legumes com pedidos finalizados via WhatsApp — sem pagamento online. Atende **Sorocaba** e **Votorantim**.

O site é um único arquivo (`index.html`) com todo o HTML, CSS e JavaScript juntos — não precisa de servidor, banco de dados ou instalação de nada. É só abrir no navegador.

---

## 📁 Estrutura do projeto

```
site-da-horta-express/
├── index.html          <- o site inteiro (HTML + CSS + JS)
├── README.md            <- este arquivo
└── produtos/             <- fotos dos produtos
    ├── morango.jpg
    ├── banana.jpg
    ├── tomate.jpg
    └── ...
```

A logo já está embutida dentro do próprio `index.html` (não depende de arquivo externo).

---

## 📦 Regras do negócio (já configuradas no site)

- **Pedidos:** domingo, terça e quinta-feira, das **7h às 15h**
- **Entregas:** segunda, quarta e sexta-feira
- **Área de entrega:** Sorocaba e Votorantim
- **Frete:** grátis acima de **R$ 50,00** — abaixo disso, taxa fixa de **R$ 10,00**
- **Pagamento:** débito, crédito, Pix ou dinheiro, **no ato da entrega** (o cliente escolhe a forma na hora de finalizar o pedido)
- **WhatsApp para receber os pedidos:** (15) 99748-5821

O site tem um painel que mostra automaticamente se os pedidos estão abertos "agora" e qual a próxima data de entrega — isso é calculado sozinho pelo horário do computador/celular de quem está vendo o site, não precisa atualizar manualmente.

---

## ✏️ Como editar os produtos e preços

Abra o `index.html` no VS Code, aperte `Ctrl+F` e procure por:

```
const PRODUTOS = [
```

Cada produto é uma linha assim:

```js
{ id:"morango", nome:"Morango", unidade:"bandeja 300g", preco:8.90, categoria:"frutas", emoji:"🍓", imagem:"produtos/morango.jpg" },
```

| Campo        | O que é                                                                 |
|--------------|--------------------------------------------------------------------------|
| `id`         | Código único do produto (não pode repetir, sem espaço ou acento)        |
| `nome`       | Nome mostrado no site                                                   |
| `unidade`    | Ex: `"kg"`, `"unidade"`, `"maço"`, `"bandeja 300g"`, `"saco 10kg"`        |
| `preco`      | Preço em número, sempre com **ponto** (ex: `7.90`, nunca `7,90`)          |
| `categoria`  | `"frutas"`, `"verduras"` ou `"legumes"`                                  |
| `emoji`      | Emoji usado como imagem enquanto não tem foto real                       |
| `imagem`     | Caminho da foto real (ex: `"produtos/morango.jpg"`) ou `null` se não tiver foto ainda |

**Adicionar produto novo:** copie uma linha inteira (do `{` até o `},`), cole antes do `]` que fecha a lista, e edite os campos.

**Remover produto:** apague a linha inteira (do `{` até o `},`).

**Alterar preço:** só troque o número depois de `preco:`.

Depois de editar, salve o arquivo (`Ctrl+S`) e atualize a página no navegador.

---

## 🖼️ Como adicionar fotos dos produtos

1. Coloque o arquivo da foto dentro da pasta `produtos/` (ex: `produtos/morango.jpg`)
2. No produto correspondente, troque `imagem:null` por `imagem:"produtos/morango.jpg"`
3. Salve e atualize o navegador — a foto substitui o emoji automaticamente

**Dicas para as fotos:**
- Prefira fotos quadradas (ex: 500x500px)
- Tente manter cada foto entre 100–300 KB para o site carregar rápido no celular
- Sites como [squoosh.app](https://squoosh.app) ajudam a redimensionar e comprimir de graça

---

## 🎨 Onde mexer no visual

Tudo fica dentro da tag `<style>` no início do arquivo.

- **Cores:** procure por `:root{` no topo do CSS — ali estão todas as variáveis de cor (`--verde-900`, `--destaque`, etc). Mudar o valor ali muda a cor em todo o site de uma vez.
- **Tamanho da logo:** procure por `.marca img` (logo do cabeçalho) e `.footer-marca img` (logo do rodapé).
- **Textos da seção "Como funciona":** procure por `id="como-funciona"` no HTML.

---

## 💬 Configurações gerais (WhatsApp, frete)

Procure no `index.html` por:

```js
const WHATSAPP_NUMERO = "5515997485821";
const FRETE_GRATIS_ACIMA_DE = 50.00;
const TAXA_ENTREGA = 10.00;
```

Esses três valores controlam pra onde vai o pedido e as regras de frete. É só mudar o número e salvar.

---

## 🚀 Como colocar o site no ar (GitHub Pages — grátis)

1. Suba os arquivos pro GitHub (repositório `site-da-horta-express`)
2. No repositório, vá em **Settings > Pages**
3. Em "Source", selecione a branch `main` e a pasta `/ (root)`
4. Clique em **Save**
5. Em alguns minutos o site estará no ar em:
   `https://willianjsilva-dev.github.io/site-da-horta-express/`

Esse link pode ser colocado na bio do Instagram.

---

## 🔄 Como atualizar o site depois de editar

Sempre que mexer no `index.html` ou adicionar fotos novas, para as mudanças aparecerem no site publicado é preciso enviar de novo pro GitHub:

```
git add .
git commit -m "descreva o que mudou aqui"
git push
```

O GitHub Pages atualiza sozinho alguns minutos depois do push.

---

## 📱 Contato

WhatsApp: **(15) 99748-5821**
Atendimento: Sorocaba e Votorantim
