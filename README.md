# 📈 Market Regime Detection with Machine Learning (BTC-USD)

Este projeto utiliza **Aprendizado Não Supervisionado (Clustering)** para identificar diferentes estados estruturais (regimes) no mercado de Bitcoin. A ideia é extrair padrões de preço, volatilidade e momentum sem a necessidade de rótulos pré-definidos.

## 🧠 Metodologia

O sistema utiliza o algoritmo **K-Means** para agrupar dados históricos do par **BTC-USD** (via Yahoo Finance) em três categorias distintas:

1.  **Bull Market (Alta):** Caracterizado por retornos positivos expressivos e momentum ascendente.
2.  **Sideways/Consolidation (Lateralização):** Períodos de baixa direção e retornos neutros/levemente negativos.
3.  **Bear Market/Crash (Baixa):** Períodos de alta volatilidade e retornos negativos acentuados.

### Feature Engineering
Para alimentar o modelo, foram calculadas as seguintes variáveis:
* **Returns:** Retorno percentual diário.
* **Volatility:** Desvio padrão móvel de 20 dias (Risco).
* **MA Ratio:** Razão entre o preço de fechamento e sua média móvel de 50 dias (Trend Presence).

## 🛠️ Tecnologias Utilizadas
* Python 3.x
* Pandas & Numpy (Manipulação de dados)
* Scikit-Learn (Machine Learning - KMeans & StandardScaler)
* YFinance (API de dados financeiros)
* Matplotlib (Visualização)

## 📊 Resultados
O modelo identificou com sucesso os regimes históricos, como as bull runs de 2021 e as correções severas de 2022.

| Regime | Retorno Médio Diário | Interpretação Econômica |
|--------|----------------------|-------------------------|
| 0      | +1.96%               | Bull Market             |
| 1      | -0.33%               | Sideways / Consolidation|
| 2      | -1.22%               | Bear Market / Crash     |

*(Insira aqui a imagem do gráfico que você gerou!)*

## 🚀 Como Executar
1. Clone o repositório
2. Instale as dependências: `pip install -r requirements.txt`
3. Execute: `python market_regime.py`
