# 🧠 Sistema de Recomendação de Produtos utilizando Algoritmo A*

## 📌 Sobre o projeto

Este projeto apresenta um protótipo de um **sistema inteligente de recomendação de produtos** desenvolvido em **Python**, utilizando o algoritmo de busca **A* (A-Star)**.

A proposta é explorar como algoritmos de busca e heurísticas podem ser aplicados na construção de soluções inteligentes, simulando um cenário onde um sistema precisa analisar possibilidades e encontrar uma recomendação baseada em critérios definidos.

Cada produto possui informações como:

- 🏷️ Nome do produto
- 📂 Categoria
- 📊 Probabilidade de conversão

Com esses dados, o algoritmo utiliza uma função heurística para avaliar as opções disponíveis e encontrar um caminho considerado mais promissor.

---

# 🎯 Objetivo do projeto

O objetivo deste projeto é aplicar conceitos de **Inteligência Artificial** e **algoritmos de busca** na criação de um protótipo de recomendação.

Durante o desenvolvimento, foram explorados conceitos como:

- Inteligência Artificial
- Algoritmos de busca
- Heurística
- Grafos
- Fila de prioridade
- Tomada de decisão baseada em critérios

Este projeto foi desenvolvido como parte da minha jornada de estudos em Inteligência Artificial após a **Imersão Agentes de IA da Alura em parceria com a Oracle**, durante a fase **Tech Builder**.

---

# 🤖 Como funciona o algoritmo A*?

O algoritmo **A*** é um algoritmo de busca utilizado para encontrar caminhos eficientes entre diferentes possibilidades.

Ele utiliza uma função de avaliação:

```text
f = g + h
```

Onde:

## 🔹 g - Custo acumulado

Representa o custo do caminho que já foi percorrido pelo algoritmo.

Exemplo:

```text
Produto A → Produto B
```

O algoritmo considera que foi necessário realizar um movimento para chegar até o próximo produto.

---

## 🔹 h - Heurística

Representa uma estimativa do potencial de uma escolha.

Neste projeto, a heurística utiliza a:

```text
probabilidade de conversão do produto
```

Produtos com maior probabilidade de conversão possuem uma avaliação mais favorável.

---

## 🔹 f - Avaliação total

Representa a soma:

```text
f = caminho percorrido + estimativa restante
```

Esse valor é utilizado pelo algoritmo para decidir qual caminho deve ser explorado primeiro.

---

# 🔎 Funcionamento do sistema

O fluxo da aplicação acontece da seguinte forma:

```
Produto inicial
      |
      ↓
Analisa produtos conectados
      |
      ↓
Verifica produtos já visitados
      |
      ↓
Calcula a heurística de cada produto
      |
      ↓
Calcula a prioridade utilizando A*
      |
      ↓
Adiciona possibilidades na fila de prioridade
      |
      ↓
Seleciona o caminho mais promissor
      |
      ↓
Retorna a recomendação encontrada
```

---

# 🏗️ Estrutura do projeto

```
📁 sistema-recomendacao-produtos-a-star

│
├── main.py
│
└── README.md
```

---

# 🧩 Componentes principais

## Classe Produto

A classe `Produto` representa cada item disponível no sistema.

Cada produto possui:

```python
nome
categoria
conversao_probabilidade
```

Exemplo:

```python
Produto(
    "Produto A",
    "Categoria 1",
    0.9
)
```

Onde:

- Produto A → nome do produto
- Categoria 1 → categoria do produto
- 0.9 → probabilidade de conversão

---

# Classe AStarRecommendation

Essa classe contém a lógica principal do algoritmo de recomendação.

Ela é responsável por:

- Criar o grafo de produtos
- Executar a busca A*
- Controlar produtos visitados
- Calcular prioridades
- Recuperar o caminho encontrado

---

# 🌐 Representação do grafo

O projeto utiliza um grafo simplificado onde cada produto pode se conectar aos demais.

Exemplo:

```
             Produto B

Produto A  ------------ Produto C

             Produto D
```

Cada produto representa um nó do grafo.

As conexões representam possibilidades de navegação entre produtos.

---

# ⚙️ Estruturas utilizadas

## Fila de prioridade (`heapq`)

O algoritmo utiliza uma fila de prioridade para organizar quais produtos serão analisados primeiro.

O A* sempre prioriza os caminhos com menor valor de:

```text
f = g + h
```

---

## Controle de visitados

O conjunto `visitados` impede que o algoritmo analise o mesmo produto diversas vezes.

Isso evita processamento desnecessário e possíveis ciclos.

---

## Registro de caminhos

O dicionário `caminhos` armazena a origem de cada produto:

Exemplo:

```python
caminhos[Produto B] = Produto A
```

Significa:

```
Produto B veio do Produto A
```

Essa informação permite reconstruir o caminho final encontrado.

---

# 🛠️ Tecnologias utilizadas

- 🐍 Python
- 🧠 Inteligência Artificial
- 🔎 Algoritmo A* (A-Star)
- 📚 Estrutura de dados
- 🕸️ Grafos
- ⚡ Fila de prioridade (`heapq`)

---

# ▶️ Como executar o projeto

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/sistema-recomendacao-produtos-a-star.git
```

---

### 2. Acesse a pasta do projeto

```bash
cd sistema-recomendacao-produtos-a-star
```

---

### 3. Execute o código

```bash
python main.py
```

---

# 📌 Exemplo de funcionamento

Produtos cadastrados:

```
Produto A
Categoria 1
Conversão: 90%

Produto B
Categoria 1
Conversão: 80%

Produto C
Categoria 2
Conversão: 70%

Produto D
Categoria 2
Conversão: 60%
```

O algoritmo analisa as possibilidades e retorna o caminho encontrado entre o produto inicial e o objetivo.

---

# 📚 Principais aprendizados

Este projeto proporcionou aprendizado prático sobre:

✅ Como funciona um algoritmo de busca inteligente

✅ Como utilizar heurísticas para auxiliar decisões

✅ Como representar problemas utilizando grafos

✅ Como funciona uma fila de prioridade

✅ Como algoritmos podem ser aplicados em sistemas inteligentes

---

# 🚀 Possíveis melhorias futuras

Algumas evoluções que podem ser implementadas:

- Integrar produtos reais de um banco de dados
- Criar uma API para disponibilizar recomendações
- Adicionar histórico de navegação do usuário
- Utilizar Machine Learning para calcular probabilidades
- Criar um sistema personalizado baseado no comportamento do cliente
- Integrar com uma aplicação web

---

# 🎓 Contexto do projeto

Projeto desenvolvido durante minha jornada de estudos em Inteligência Artificial, após participar da:

**Imersão Agentes de IA - Alura + Oracle**

Durante a fase **Tech Builder**, explorando conceitos de agentes inteligentes, algoritmos de busca e aplicações práticas de IA.

---

# 👨‍💻 Autor

**João Victor Sitta**

Estudante de Desenvolvimento de Software e Inteligência Artificial.

Buscando transformar conhecimento em projetos práticos e explorar novas possibilidades utilizando tecnologia.

---

⭐ Se este projeto ajudou você a entender um pouco mais sobre algoritmos de busca inteligente, fique à vontade para explorar o código!
