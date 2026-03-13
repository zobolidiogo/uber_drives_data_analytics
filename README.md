# Análise Exploratória de Dados — Uber Ride Analytics

## Introdução

Este projeto foi produzido como atividade extra do curso Introdução à Inteligência Artificial (SCTEC, SENAI) e apresenta uma Análise Exploratória de Dados (AED) utilizando o conjunto de dados **Uber Ride Analytics Dashboard**, disponível na plataforma Kaggle. O objetivo da análise é compreender padrões de utilização do serviço de transporte por aplicativo, identificando comportamentos relevantes relacionados à demanda, características das corridas e variações temporais presentes nos dados.

A análise exploratória de dados é uma etapa fundamental em projetos de Ciência de Dados e Inteligência Artificial, pois permite compreender a estrutura do dataset, identificar padrões, verificar possíveis inconsistências e gerar hipóteses que podem posteriormente ser utilizadas em modelos de aprendizado de máquina.

## Dataset

O conjunto de dados utilizado neste projeto pode ser encontrado pelo link:
[kaggle.com/datasets/yashdevladdha/uber-ride-analytics-dashboard](https://www.kaggle.com/datasets/yashdevladdha/uber-ride-analytics-dashboard)

Ele contém informações relacionadas a corridas realizadas por meio de um serviço de transporte por aplicativo. O dicionário de dados inicial está abaixo:

| Column Name                       | Descrição                                                                                         | Tipo de Dado |
| --------------------------------- | ------------------------------------------------------------------------------------------------- | ------------ |
| Date                              | Data da reserva/corrida                                                                           | Data         |
| Time                              | Horário da reserva/corrida                                                                        | Hora         |
| Booking ID                        | Identificador único de cada reserva de corrida                                                    | Texto        |
| Booking Status                    | Status da corrida (Concluída, Cancelada pelo Cliente, Cancelada pelo Motorista, etc.)             | Texto        |
| Customer ID                       | Identificador único do cliente                                                                    | Texto        |
| Vehicle Type                      | Tipo de veículo (Go Mini, Go Sedan, Auto, eBike/Bike, UberXL, Premier Sedan)                      | Texto        |
| Pickup Location                   | Local de origem da corrida                                                                        | Texto        |
| Drop Location                     | Destino da corrida                                                                                | Texto        |
| Avg VTAT                          | Tempo médio para o motorista chegar ao local de embarque (em minutos)                             | Decimal      |
| Avg CTAT                          | Tempo médio da viagem entre origem e destino (em minutos)                                         | Decimal      |
| Cancelled Rides by Customer       | Indicador de corrida cancelada pelo cliente                                                       | Booleano     |
| Reason for cancelling by Customer | Motivo do cancelamento realizado pelo cliente                                                     | Texto        |
| Cancelled Rides by Driver         | Indicador de corrida cancelada pelo motorista                                                     | Booleano     |
| Driver Cancellation Reason        | Motivo do cancelamento realizado pelo motorista                                                   | Texto        |
| Incomplete Rides                  | Indicador de corrida incompleta                                                                   | Booleano     |
| Incomplete Rides Reason           | Motivo da corrida ter sido marcada como incompleta                                                | Texto        |
| Booking Value                     | Valor total da corrida                                                                            | Decimal      |
| Ride Distance                     | Distância percorrida durante a corrida (em km)                                                    | Decimal      |
| Driver Ratings                    | Avaliação recebida pelo motorista (escala de 1 a 5)                                               | Decimal      |
| Customer Rating                   | Avaliação dada pelo cliente (escala de 1 a 5)                                                     | Decimal      |
| Payment Method                    | Método de pagamento utilizado (UPI, Dinheiro, Cartão de Crédito, Carteira Uber, Cartão de Débito) | Texto        |

Esses dados permitem analisar padrões de uso do serviço ao longo do tempo e observar relações entre diferentes variáveis presentes no conjunto de dados.

## Tecnologias utilizadas

- Python
- Pandas
- Matplotlib
- Seaborn
- Jupyter Notebook

## Preparação e Limpeza dos Dados

Antes da realização das análises, foi necessário realizar algumas etapas de preparação dos dados, incluindo:

* Verificação de valores ausentes (NaN)
* Tratamento de colunas com tipos de dados incorretos
* Conversão de colunas de data e hora para o formato datetime
* Criação de variáveis derivadas, como hora do dia e mês
* Organização das variáveis para facilitar a análise estatística e visual

Essas etapas são importantes para garantir a qualidade dos dados e evitar distorções nas análises posteriores.

## Análise Exploratória

Durante a análise exploratória foram realizadas diversas observações sobre o comportamento dos dados, incluindo:

* Análise de correlação entre variáveis numéricas
* Identificação de padrões de demanda ao longo do dia
* Relação entre distância percorrida e valor da corrida
* Distribuição temporal das corridas
* Visualizações gráficas para facilitar a interpretação dos resultados

Para isso, foram utilizadas bibliotecas da linguagem Python voltadas para análise e visualização de dados, como **Pandas**, **Matplotlib** e **Seaborn**.

## Visualizações

Foram geradas diferentes visualizações gráficas para auxiliar na compreensão dos dados, entre elas:

* Heatmap de correlação entre variáveis
* Gráficos de dispersão (scatter plots)
* Gráficos de linha para análise temporal
* Análise de distribuição de corridas ao longo do dia

Essas visualizações ajudam a identificar padrões importantes e facilitam a interpretação dos dados analisados.

## Estrutura do projeto

```
uber_drives_data_analytics/
│
├── visualizacoes/
│   ├── dispersao_chegada_destino.png      # Gráfico de dispersão analisando relação entre locais de chegada e destino das corridas
│   ├── dispersao_distancia_valor.png      # Gráfico de dispersão mostrando relação entre distância da corrida e valor pago
│   ├── hist_cliente_destino.png           # Histograma relacionado às avaliações ou distribuição de clientes e destinos
│   ├── hist_motorista_cliente.png         # Histograma comparando avaliações entre motoristas e clientes
│   ├── hist_valor_caronas.png             # Histograma mostrando a distribuição dos valores das corridas
│   ├── linhas_corridas.png                # Gráfico de linhas mostrando quantidade de corridas ao longo do tempo
│   └── matriz_correlação.png              # Heatmap da matriz de correlação entre variáveis numéricas
│
├── README.md                              # Documentação do projeto explicando objetivo, dataset e análise realizada
│
├── codigo_fonte.ipynb                     # Notebook principal contendo todo o código de limpeza, análise exploratória e geração dos gráficos
│
└── dataframe_uber.csv                     # Dataset utilizado na análise exploratória de dados
```

## Resultados das análises

A análise exploratória permitiu identificar alguns padrões relevantes no conjunto de dados. Os gráficos de dispersão indicam que o valor das corridas não apresenta uma correlação forte apenas com a distância percorrida, sugerindo que outros fatores podem influenciar significativamente o preço final da viagem, como tempo de espera, localização, tipo de veículo ou condições de demanda. Isso indica que modelos de aprendizado de máquina poderiam ser utilizados no futuro para prever valores de corridas considerando múltiplas variáveis simultaneamente.

A análise da distribuição dos tempos mostra que a maior parte das corridas apresenta um tempo médio de chegada do motorista ao cliente entre aproximadamente 2 e 15 minutos. Já o tempo médio de deslocamento entre o ponto de embarque e o destino tende a concentrar-se principalmente entre 15 e 45 minutos, indicando que a maioria das viagens possui duração relativamente curta ou moderada.

Em relação aos valores das corridas, observa-se uma distribuição ampla, variando aproximadamente entre 0 e 500 unidades monetárias. Valores mais elevados aparecem com menor frequência e podem representar possíveis outliers ou corridas atípicas, como viagens mais longas ou serviços de categoria superior.

Por fim, a análise temporal do número de corridas ao longo dos meses mostra que a demanda permanece relativamente estável durante o ano, com pequenas variações. Observa-se um pico de corridas no mês de julho, enquanto fevereiro apresenta o menor volume registrado. No geral, as oscilações mensais são moderadas, sugerindo um padrão de utilização relativamente consistente do serviço ao longo do período analisado.

## Conclusão

A análise exploratória permitiu identificar diferentes padrões relacionados ao uso do serviço de transporte por aplicativo, como variações na demanda ao longo do tempo e relações entre características das corridas. Esses insights podem servir como base para análises mais avançadas no futuro, incluindo o desenvolvimento de modelos de Inteligência Artificial para previsão de demanda, estimativa de preços ou classificação de padrões de uso.

Este projeto demonstra a aplicação prática de conceitos introdutórios de análise de dados utilizando Python e ferramentas amplamente utilizadas na área de Ciência de Dados.

## Contato

Diogo Zoboli

zobolidiogo@gmail.com

Linkedin: [linkedin.com/in/zobolidiogo](https://www.linkedin.com/in/zobolidiogo)

Github: [github.com/zobolidiogo](https://github.com/zobolidiogo)
