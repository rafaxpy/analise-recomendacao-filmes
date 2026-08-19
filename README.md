# Estudo de Caso: Análise Estatística e Recomendação de Filmes 🎬📊

Este repositório contém um estudo de caso focado na análise estatística de um conjunto de dados de avaliações de filmes (baseado no MovieLens) e na preparação da base para a construção de um algoritmo de Sistema de Recomendação.

## 🎯 Objetivo do Projeto
O objetivo principal deste projeto é realizar a ingestão, o tratamento e a análise exploratória de um grande volume de interações entre usuários e filmes, chegando na separação adequada dos dados para a validação de perfis de usuários em modelos de Machine Learning.

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Manipulação de Dados:** Pandas
* **Visualização de Dados:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn

## 🗂️ Estrutura e Tratamento dos Dados

Os dados utilizados foram disponibilizados pelo grupo de pesquisa **GroupLens**.
* **Dataset:** MovieLens 10M Dataset
* **Link Oficial:** [GroupLens - MovieLens 10M](https://grouplens.org/datasets/movielens/10M/)

Os dados originais foram extraídos de arquivos no formato `.dat`, separados pelo delimitador personalizado `::`.

As seguintes etapas de pré-processamento foram realizadas:
1. Configuração de motores de leitura (`engine='python'`) para lidar com delimitadores.
2. Conversão de valores Timestamp para o formato legível `datetime`.
3. Extração do gênero principal de cada filme a partir de strings agrupadas.
4. Relacionamento entre as avaliações dos usuários e o catálogo de filmes utilizando a chave `Id_Filme`.

## 📈 Análise Exploratória
A análise descritiva permitiu compreender a distribuição e o engajamento na plataforma:
* **Métricas:** Quantificação total de usuários únicos (69.878), filmes e avaliações, além do cálculo da média geral da plataforma.
* **Análise por Gênero:** Cálculo de estatísticas detalhadas para cada gênero de filme, incluindo:
  * Média e Mediana
  * Valores Mínimos e Máximos
  * Amplitude e Desvio Padrão
* **Visualização de Gráfico:** Construção de gráficos de barras horizontais contrastando a avaliação média de cada gênero com a média global, permitindo identificar quais categorias destoam do padrão.

## 🧪 Estratégia de Amostra de Treino e Teste
Para garantir a validação correta do algoritmo de recomendação, a base de dados foi segmentada mantendo o perfil de consumo de cada indivíduo. 
* **Proporção:** 70% para Treino e 30% para Teste.
* **Técnica:** Amostragem Estratificada (`stratify`) baseada na classe `Id_Usuario`.
* **Resultado:** Garantiu-se matematicamente que todos os usuários estão presentes em ambas as bases, evitando distorções no aprendizado e na validação do modelo de recomendação.

## 🚀 Como Executar o Projeto

1. Clone este repositório:
   ```bash
   git clone https://github.com/rafaxpy/analise-recomendacao-filmes.git
   ```

2. Instale as dependências necessárias:
    ```bash
    pip install pandas matplotlib seaborn scikit-learn
    ```

3. Execute o Jupyter Notebook:
    ```bash
    jupyter notebook "Estudo de caso - Análise Estatística.ipynb"
    ```