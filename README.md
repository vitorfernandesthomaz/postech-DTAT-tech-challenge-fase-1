# Tech Challenge - Fase 1 | Olist: Eficiência Geo-Estratégica

## 📌 Sobre o projeto

Este repositório contém os entregáveis do **Tech Challenge - Fase 1**, desenvolvido com base no **Brazilian E-Commerce Public Dataset by Olist**.

O objetivo do projeto foi transformar dados transacionais de e-commerce em uma análise executiva voltada a investidores e diretores, com foco em **eficiência logística, desempenho regional, custo de frete e oportunidades de expansão de mercado**.

A análise foi construída a partir de dados reais e anonimizados da Olist, considerando pedidos realizados entre **2016 e 2018**.

---

## 🎯 Pergunta executiva

**Onde a Olist está perdendo eficiência logística — e onde isso vira oportunidade de expansão?**

A partir dessa pergunta, o projeto buscou identificar:

- quais estados apresentam maior tempo médio de entrega;
- como o custo médio de frete se relaciona com o prazo de entrega;
- quais regiões combinam alto potencial econômico com baixa eficiência logística;
- onde a Olist poderia priorizar investimentos em infraestrutura logística.

---

## 🧠 Resumo executivo

A análise validada considerou **96.446 pedidos entregues válidos** entre 2016 e 2018.

Os resultados indicaram uma disparidade logística relevante no Brasil. Enquanto São Paulo apresenta lead time médio próximo de **8,8 dias**, estados do Norte e Nordeste apresentam prazos significativamente maiores, chegando a mais de **18 a 29 dias** em algumas UFs.

Além do prazo, também foi identificada maior pressão de frete nas regiões mais distantes da malha logística principal. Isso reforça que o problema não é apenas operacional, mas também estratégico.

A recomendação executiva do projeto é iniciar uma estratégia de **regionalização logística no Nordeste**, priorizando um hub regional em **Salvador (BA)** e uma segunda onda de expansão para **Recife (PE)**.

---

## 📊 Principais indicadores analisados

| UF | Pedidos | Lead time médio | Frete médio | Trânsito logístico | Review médio |
|---|---:|---:|---:|---:|---:|
| SP | 40.479 | 8,8 dias | R$ 17,33 | 5,6 dias | 4,25 |
| RJ | 12.349 | 15,3 dias | R$ 23,95 | 12,0 dias | 3,97 |
| PE | 1.593 | 18,4 dias | R$ 35,83 | 15,2 dias | 4,08 |
| BA | 3.256 | 19,3 dias | R$ 29,96 | 16,0 dias | 3,93 |
| MA | 717 | 21,6 dias | R$ 42,95 | 18,0 dias | 3,83 |
| AM | 145 | 26,4 dias | R$ 37,45 | 23,5 dias | 4,24 |

---

## 🧪 Metodologia

A análise foi desenvolvida em Python, utilizando o Google Colab.

### Etapas principais:

1. **Carregamento das bases**
   - pedidos;
   - clientes;
   - itens dos pedidos;
   - vendedores;
   - pagamentos;
   - avaliações;
   - produtos;
   - geolocalização.

2. **Tratamento dos dados**
   - conversão de colunas de data;
   - filtro de pedidos com status `delivered`;
   - remoção de registros com datas nulas ou inválidas;
   - cálculo do lead time em dias;
   - cálculo do tempo de trânsito logístico;
   - consolidação dos dados por `order_id`.

3. **Governança da análise**
   - a unidade principal de análise foi o pedido único (`order_id`);
   - o frete foi calculado como soma do `freight_value` dos itens do pedido;
   - pedidos com múltiplos itens foram tratados para evitar duplicidade;
   - os resultados foram agregados por UF do cliente.

4. **Enriquecimento externo**
   - utilização de participação aproximada no PIB nacional por UF;
   - cruzamento entre potencial econômico e eficiência logística.

---

## 📈 Principais análises

### 1. Ranking de tempo médio de entrega por estado

A análise identificou que os maiores tempos médios de entrega estão concentrados principalmente em estados do Norte e Nordeste.

Esse resultado indica que o desafio logístico é estrutural e está relacionado à distância da malha principal de distribuição.

---

### 2. Custo de frete vs. prazo de entrega

O cruzamento entre frete médio e prazo de entrega mostrou que algumas UFs combinam dois problemas simultâneos:

- frete mais caro;
- entrega mais lenta.

Essa combinação representa risco de pior experiência do cliente e perda de competitividade regional.

---

### 3. Matriz de expansão estratégica

A matriz de expansão cruzou:

- participação aproximada no PIB nacional;
- lead time médio;
- volume de pedidos;
- frete médio.

A partir dessa análise, a Bahia foi identificada como prioridade regional para um piloto logístico, seguida por Pernambuco como segunda onda de expansão.

---

## 🚀 Recomendação estratégica

A recomendação principal é implementar um **hub regional em Salvador (BA)**, com expansão posterior para **Recife (PE)**.

### Objetivos da recomendação:

- aproximar estoque dos clientes do Nordeste;
- reduzir dependência de rotas longas a partir do Sudeste;
- diminuir prazo médio de entrega;
- reduzir pressão de frete em rotas críticas;
- melhorar experiência do cliente;
- ampliar competitividade regional.

---

## 🗺️ Plano de implementação

| Etapa | Período | Descrição |
|---|---|---|
| Análise | 0–30 dias | Mapeamento de rotas, sellers e categorias prioritárias |
| Piloto | 31–90 dias | Operação inicial com parceiros locais em Salvador |
| Integração | 90–180 dias | Monitoramento de SLAs, frete e lead time |
| Expansão | 180+ dias | Replicação para Pernambuco e rotas adjacentes |

---

## 📌 Impacto esperado

Os percentuais abaixo são tratados como **cenários executivos de impacto esperado**, e não como resultados históricos já comprovados:

- até **-50%** de redução potencial de prazo em rotas priorizadas;
- **-30% a -35%** de redução potencial de frete;
- aumento esperado de satisfação, review e recompra.

O que foi comprovado pelo dataset é a existência do gargalo: prazos e fretes mais elevados em UFs distantes da malha logística principal.

---

## 📦 Entregáveis

### 1. Código utilizado

O notebook principal do projeto está disponível neste repositório:

- `TechChallenge_FASE_1_VF.ipynb`

Nele estão documentadas as etapas de carregamento, tratamento, análise e geração dos gráficos.

---

### 2. Relatório executivo

O relatório executivo está disponível em:

- `Relatorio Executivo - TechChallenge - Fase 1.pdf`

O documento apresenta contexto, metodologia, diagnóstico logístico, matriz de oportunidade, recomendações executivas e limites da análise.

---

### 3. Apresentação executiva

A apresentação utilizada no vídeo está disponível em:

- `Apresentacao_Olist_Eficiencia_Geo_Estrategica.pdf`

A apresentação foi estruturada com foco em storytelling executivo, conectando diagnóstico, oportunidade, plano de ação e impacto esperado.

---

### 4. Vídeo executivo

O vídeo executivo gravado para apresentação do projeto está disponível em:

- `Olist_Eficiencia_Geo_Estrategica_video.mp4`

O vídeo apresenta a análise em linguagem executiva, com foco em tomada de decisão.

---

## 🛠️ Ferramentas utilizadas

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- PowerPoint
- GitHub

---

## ✅ Conclusão

A análise mostra que a logística no e-commerce brasileiro não deve ser tratada apenas como custo operacional.

No caso analisado, a logística aparece como uma alavanca direta de crescimento, experiência do cliente e competitividade regional.

Os dados indicam que a regionalização no Nordeste, iniciando por Salvador e expandindo posteriormente para Pernambuco, é a rota mais coerente para transformar gargalos logísticos em vantagem competitiva.

---

## 👤 Autor

**Vitor Augusto Fernandes Thomaz de Aquino**  
RM: 372301  
Grupo: 82  
Tech Challenge | Pós-Tech
