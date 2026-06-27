# T-Pizza

## Visão Geral

O **T-Pizza** é uma evolução do sistema **T-Burguer**, desenvolvido em Vue 3 durante as aulas de Desenvolvimento Web.

A proposta do projeto foi adaptar a base original de uma hamburgueria para um novo segmento comercial: uma **pizzaria artesanal**.

Foram preservadas a estrutura principal do projeto, a organização por componentes, o uso de rotas, o fluxo de cadastro de pedidos e a comunicação com uma API mockada utilizando **JSON Server**. Toda a customização foi realizada sobre a base estrutural desenvolvida em sala de aula, respeitando a metodologia proposta para a disciplina.

---

# Principais Alterações Realizadas

O sistema foi adaptado visual e estruturalmente para o segmento de pizzaria.

### Entre as alterações realizadas estão:

- Substituição da identidade visual para **T-Pizza**;
- Alteração do cardápio de hambúrgueres para pizzas;
- Substituição do campo **"Ponto da Carne"** por **"Tipo de Massa"**;
- Atualização de textos, cores, logotipo, banner e imagens;
- Adaptação dos adicionais e bebidas para o novo segmento;
- Ajustes no layout da tela de configuração do pedido;
- Implementação de alertas semânticos para validação do formulário;
- Redirecionamento automático após confirmação do pedido;
- Atualização dinâmica da lista de pedidos após alteração de status e exclusão.

### Exemplo da estrutura utilizada para criação do pedido:

```javascript
const dadosPedido = {
  nome: this.nomeCliente,
  ponto: this.pontoCarneSelecionado,
  bebidas: [...this.listaBebidasSelecionadas],
  complemento: [...this.listaComplementosSelecionados],
  burguer: this.burguer,
  statusId: 5,
};
```

Apesar de alguns nomes internos ainda preservarem a estrutura original do T-Burguer (como a propriedade `burguer`), toda a interface, os dados apresentados e a experiência do usuário foram adaptados para o contexto de uma pizzaria, mantendo fidelidade técnica à base desenvolvida em sala.

---

# Solução Técnica dos Alertas

A validação dos campos obrigatórios foi implementada diretamente no componente de pedido utilizando o gerenciamento de estado do Vue 3.

Foram criadas duas variáveis responsáveis pelo controle dos alertas:

```javascript
mensagem: "",
tipoMensagem: "",
```

A função `mostrarMensagem` recebe dinamicamente o texto e o tipo do alerta:

```javascript
mostrarMensagem(texto, tipo) {
  this.mensagem = texto;
  this.tipoMensagem = tipo;
}
```

No template, o alerta é exibido somente quando existe uma mensagem ativa:

```html
<div v-if="mensagem" class="alerta" :class="tipoMensagem">
  {{ mensagem }}
</div>
```

As classes CSS representam semanticamente cada tipo de feedback:

```css
.sucesso {
  background: #2e7d32;
}

.erro {
  background: #d32f2f;
}

.aviso {
  background: #ef6c00;
}

.info {
  background: #1565c0;
}
```

Dessa forma, o sistema comunica visualmente erros de preenchimento, avisos, informações e confirmações de sucesso ao usuário.

---

# Funcionalidades

- Listagem das pizzas disponíveis;
- Seleção da pizza;
- Cadastro de pedidos;
- Validação do nome do cliente;
- Validação do tipo de massa;
- Seleção de adicionais;
- Seleção de bebidas;
- Alertas visuais semânticos;
- Redirecionamento automático para a tela de pedidos;
- Listagem dos pedidos realizados;
- Alteração do status dos pedidos;
- Exclusão dinâmica dos pedidos.

---

# Tecnologias Utilizadas

- Vue 3
- Vue Router
- JavaScript
- HTML5
- CSS3
- JSON Server
- Render
- Vercel
- GitHub

---

# Link da API

### API mockada (JSON Server) publicada no Render:

https://tpizza-api.onrender.com

### Endpoints principais:

```
/menu
/opcionais
/tipos_pontos
/status_pedido
/pedidos
```

---

# Link de Produção

### Sistema publicado na Vercel:

https://tpizza-seven.vercel.app/

---

# Link do Repositório

### Front-end:

https://github.com/th-mFerreira/tpizza

### API (JSON Server):

https://github.com/th-mFerreira/tpizza-api

---

# Como Executar Localmente

### Clone o repositório:

```bash
git clone https://github.com/th-mFerreira/tpizza.git
```

### Acesse a pasta:

```bash
cd tpizza
```

### Instale as dependências:

```bash
npm install
```

### Execute o JSON Server:

```bash
npm run bancojson
```

### Em outro terminal execute o projeto Vue:

```bash
npm run serve
```

### Acesse no navegador:

```
http://localhost:8080
```

---

# Autor

**Miguel Ferreira**

Projeto Final desenvolvido para a disciplina de **Desenvolvimento Web**, utilizando Vue 3, JSON Server e os conceitos trabalhados durante as aulas.
