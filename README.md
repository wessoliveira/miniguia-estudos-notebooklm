# Contexto e Objetivos
O tema escolhido para elaborar um guia de estudos pelo NotebookLM foi Estatística: distribuições de probabilidade e suas aplicações. O intuito é ter uma visão ampla, porém simples de entender, das principais variáveis aleatórias e suas distribuições, com exemplos de aplicação.

# Curadoria de Fontes
Para encontrar as fontes foram observados os resultados de duas buscas no Google.
1) aprender estatística principais distribuições de probabilidade com aplicações reais e exercícios resolvidos

   Esta busca retornou uma importante fonte, que é o livro Estatística e Probabilidade, com autoria de Francisco de Assis Amaral Bastos, disponível em PDF no link: [Estatística e Probabilidade](https://www.uece.br/cct/wp-content/uploads/sites/28/2021/07/LIVRO-ESTATI%CC%81STICA-E-PROBABILIDADE.pdf)

   Outro material importante em PDF são os slides de aula da disciplina Probabilidade e Estatística da professora Raquel Sampaio, ministrada na Escola de Ciências e Tecnologia - UFRN. Todos os arquivos PDF encontram-se no repositório: [Aulas Probabilidade e Estatística](https://pessoal.ect.ufrn.br/~rbatista/files/pe/aulas/)

   Há também algumas páginas com conteúdo interessante sobre as distribuições e aplicação delas com a linguagem R.

   [Distribuições de Probabilidade - UFBA](https://rpubs.com/estatisticaufba/distribuicaodeprobabilidade)

   [Apostila R - Distribuições de Probabilidade - UFMG](https://www.est.ufmg.br/~monitoria/Material/ApostilaR/DistribuicoesProbabilidade.html)

   [Introdução ao R para alunos de ciências exatas](https://bookdown.org/matheusogonzaga/apostila_r2/distribuicoes-de-probabilidade.html)

2) aplicações reais das distribuições de probabilidades discretas e contínuas

   Nesta busca o destaque está para o material de aulas da disciplina Introdução à Estatística na EACH/USP sobre variáveis aleatórias. O PDF dos slides está disponível no link: [Variáveis Aleatórios - EACH/USP](https://www.each.usp.br/lauretto/ACH2053_2018/T03%20-%20Variaveis%20Aleatorias.pdf)

   Páginas úteis também são listadas:

   [DataCamp - Discrete probability distributions explained with examples](https://www.datacamp.com/tutorial/discrete-probability-distributions-explained-with-examples)
   
   [ProfessorGuru - Distribuição de Probabilidades de Variáveis Aleatórias](https://professorguru.com.br/estatistica/distribuicao-variaveis.html)

# Engenharia de Prompts e "Cicatrizes"

Para avanço no entendimento do assunto foram testados alguns prompts:

## 1) O que diferencia um experimento aleatório de um espaço amostral?

   _Esta resposta se baseou nas fontes em PDF: "Aula 4 - Probabilidade conceitos básicos – Parte 1" e o livro "Estatística e Probabilidade"._
   
   **Experimento aleatório** é a **ação, processo ou fenômeno incerto** que, quando repetido sob as mesmas condições, pode produzir resultados diferentes e imprevisíveis. Trata-se do procedimento prático ou do evento que estamos observando no mundo real.

   Por outro lado, o **espaço amostral** (geralmente denotado por $S$) é o **conjunto matemático** de todos os resultados possíveis que podem decorrer da realização desse experimento. Para ser considerado o espaço amostral de um experimento, esse conjunto deve garantir que apenas um resultado ocorra em cada repetição e que nenhuma possibilidade viável fique de fora.

   **A Diferença Fundamental**

   •	**Experimento Aleatório**: É o **ato ou fenômeno dinâmico** em si (por exemplo, o ato físico de lançar um dado ou medir a altura de alguém).

   •	**Espaço Amostral**: É a **estrutura matemática estática** que lista todas as alternativas que podem acontecer a partir desse ato (por exemplo, o conjunto de números ou de medidas possíveis).

   **Exemplos Comparativos**

   Para ilustrar a relação e a diferença de forma clara, considere os seguintes cenários práticos:
   
   1.	Lançamento de um dado: 
   
         o	Experimento Aleatório ($E_1$): O ato de lançar o dado e anotar o número mostrado na face superior.

         o	Espaço Amostral ($S_1$): O conjunto numérico finito correspondente a todas as faces: $S_1 = {1, 2, 3, 4, 5, 6}$.

   2.	Lançamento de uma moeda até obter a primeira cara: 

     	o	Experimento Aleatório ($E_2$): Jogar repetidamente a moeda até que apareça uma cara e anotar a sequência obtida.

     	o	Espaço Amostral ($S_2$): O conjunto de sequências possíveis (onde $C$ é cara e $K$ é coroa), que neste caso é infinito: $S_2 = {C, KC, KKC, KKKC, ...}$.

   3.	Teste de durabilidade de uma lâmpada: 

     	o	Experimento Aleatório ($E_3$): Testar a lâmpada e registrar o tempo de funcionamento contínuo até ela queimar.

     	o	Espaço Amostral ($S_3$): O conjunto de todos os tempos reais possíveis (contínuo): $S_3 = {t \in \mathbb{R} \mid t \ge 0}$.
   
   Enquanto o experimento é a ação prática que gera a incerteza, o espaço amostral é o primeiro passo matemático que tomamos para mapear e analisar essas incertezas de maneira formal.

## 2) Como funcionam as variáveis aleatórias?

   _Esta resposta se baseou nas fontes em PDF: "Aula 5 - Probabilidade Distribuições Discretas - Parte 1", "Aula 6 - Probabilidade Distribuições Contínuas - Parte 1" e "T03 - Variáveis Aleatórias" e também nas páginas do Professor Guru e a Apostila R (UFMG)._

   Uma variável aleatória funciona como uma ponte ou regra matemática que traduz os resultados qualitativos ou incertos de um experimento aleatório em valores numéricos reais. Em termos formais, ela é definida como uma função que associa cada elemento do espaço amostral $S$ (os resultados possíveis de um experimento) a um número real.

   Para denotar esse mapeamento, costuma-se representar a variável aleatória com letras maiúsculas (como $X$) e os possíveis valores específicos que ela pode assumir com letras minúsculas (como $x$).
      •	Exemplo Prático: Imagine um estudante ligando para a coordenação. Ele pode ter sorte e ser atendido imediatamente (evento de sucesso, $S$) ou ficar na fila de espera (evento de fracasso, $F$). O espaço amostral original desse experimento é qualitativo: $S = {S, F}$. Podemos definir uma variável aleatória $X$ que associe $X(S) = 1$ e $X(F) = 0$. Ao fazer isso, transformamos o evento incerto em dados numéricos manipuláveis.

   ________________________________________

   Como as Variáveis Aleatórias se Classificam?

   Dependendo da estrutura do espaço amostral ao qual estão associadas, as variáveis aleatórias são divididas em duas grandes classes:

   1. Variáveis Aleatórias Discretas
   
      Uma variável aleatória é discreta se ela assume apenas um número finito de valores ou uma sequência infinita contável (enumerável). Na prática, são variáveis cujos resultados possíveis podem ser listados.
   
      •	Exemplos: O número de acidentes em um trecho de rodovia durante um mês, o número de ligações recebidas por dia em um escritório ou a quantidade de caras obtidas no lançamento de uma moeda.
   
      •	Como funciona a probabilidade (f.p. ou f.m.p.): O comportamento de uma variável discreta é ditado por sua função de probabilidade (f.p.) ou função massa de probabilidade (f.m.p.). Essa função atribui a probabilidade exata de a variável assumir cada valor específico: $\[f(x) = P(X = x)\]$. Como regra matemática básica, a soma das probabilidades de todos os valores possíveis de $X$ deve ser exatamente igual a 1.
   
   2. Variáveis Aleatórias Contínuas
   
   Uma variável aleatória é contínua se ela pode assumir qualquer valor numérico dentro de um intervalo ou de uma união de intervalos na reta real. Trata-se de uma escala contínua de valores infinitos e não-enumeráveis.
   
   •	Exemplos: A altura de um cidadão selecionado ao acaso, a profundidade de um ponto sorteado em um lago ou o tempo até que uma lâmpada queime.
   
   •	Como funciona a probabilidade (f.d.p.): Diferente das discretas, a probabilidade de uma variável contínua assumir um valor pontual exato é sempre igual a zero, ou seja, $P(X = x) = 0$. Por isso, em distribuições contínuas, calculamos probabilidades para intervalos de valores. O comportamento de variáveis contínuas é descrito por uma função densidade de probabilidade (f.d.p.), representada por $f(x)$. A probabilidade de a variável $X$ pertencer ao intervalo $[a, b]$ é dada pela área sob a curva dessa função no respectivo intervalo, calculada via integral: $\[P(a \le X \le b) = \int_{a}^{b} f(x) dx\]$. A área total sob toda a curva da f.d.p. deve ser igual a 1.

   ________________________________________
   
   Ferramentas de Análise e Modelagem
   
   Independentemente do tipo de variável aleatória, existem conceitos matemáticos universais para descrevê-las:
   
   •	Função de Distribuição Acumulada (FDA ou $F(x)$): É uma função que acumula a probabilidade acumulada até um determinado valor $x$, ou seja, $F(x) = P(X \le x)$. 
   
      o	No caso discreto, ela simplesmente "soma" as probabilidades de todos os valores menores ou iguais a $x$.
   
      o	No caso contínuo, ela integra a densidade de probabilidade desde $-\infty$ até $x$.
   
      o	Uma grande vantagem de se obter a FDA é simplificar cálculos de intervalos, uma vez que $P(a \le X \le b) = F(b) - F(a)$.
   
   •	Medidas de Resumo (Média e Dispersão): Para caracterizar de forma rápida o comportamento de uma variável, usamos o Valor Esperado (Média ou Esperança Matemática), que representa o comportamento de longo prazo ou centro da população, e a Variância, que quantifica a dispersão ou o distanciamento dos valores em torno dessa média.



# Miniguia de Estudo

## Resumos estruturados do assunto

### Fundamentos da Teoria da Probabilidade: Estrutura, Modelagem e Análise de Incerteza

A probabilidade não deve ser compreendida apenas como um apêndice da matemática, mas como o arcabouço formal e rigoroso que viabiliza a transição do pensamento determinístico para o estocástico. Como especialistas em modelagem, entendemos que a definição precisa dos elementos de incerteza é o que permite transformar fenômenos aparentemente caóticos — da vida útil de componentes eletrônicos à eficácia de procedimentos clínicos — em modelos matemáticos tratáveis e preditivos.

1. A Gênese da Incerteza: Experimentos Aleatórios e Espaços Amostrais

A formalização da incerteza inicia-se com a caracterização do experimento aleatório: um processo que, sob condições de repetibilidade idênticas, é capaz de produzir resultados distintos e imprevisíveis individualmente. A primeira etapa crítica da modelagem é a descrição exaustiva do Espaço Amostral (S), o conjunto universo de todos os resultados possíveis. Para que S possua validade matemática e suporte inferências robustas, ele deve cumprir dois requisitos axiomáticos: a unicidade de resultado (apenas um ponto amostral ocorre por rodada) e a cobertura total (nenhum resultado possível pode ser omitido).

Taxonomia de Espaços Amostrais

A natureza de S dita a "gramática" analítica a ser empregada:

* Enumerável e Finito: Conjunto de resultados com cardinalidade bem definida.
  * Exemplo: Lançamento de um dado balanceado ($S=\{1, 2, 3, 4, 5, 6\}$).
* Enumerável e Infinito: Resultados que podem ser listados em uma sequência, mas não possuem limite superior.
  * Exemplo: Lançamento sucessivo de uma moeda até a ocorrência da primeira cara ($S=\{C, KC, KKC, \dots\}$).
* Não-enumerável: Resultados que formam um continuum, geralmente associados a medições físicas.
  * Exemplo: Lançamento de um dardo em alvo circular de raio 1, onde o resultado é um par ($x,y$) tal que $x^2 + y^2 \le 1$.

Impacto Analítico ("E daí?"): A distinção entre esses tipos é o divisor de águas entre a contagem combinatória e o cálculo integral. Em espaços enumeráveis, operamos com somatórios (\sum) e análise combinatória para determinar pesos. Em espaços não-enumeráveis, entramos no domínio da probabilidade geométrica ou cálculo de densidades, onde a probabilidade de um ponto isolado é nula e a chance de um evento é definida pela medida (comprimento, área ou volume) do subconjunto sobre a medida total de S.

2. Variáveis Aleatórias: A Ponte entre Eventos e Números

A transição para Variáveis Aleatórias representa o salto ontológico da observação qualitativa para o domínio da Modelagem Estocástica. Trata-se de uma função que mapeia resultados do espaço amostral em valores numéricos, permitindo que eventos complexos sejam analisados via ferramentas estatísticas avançadas.

Diferenciação Crucial: Variáveis Discretas vs. Contínuas

Característica	Variáveis Discretas	Variáveis Contínuas
Natureza do Conjunto	Resultados de contagem (valores isolados).	Resultados de medição (intervalos reais).
Função Matemática	Função Massa de Probabilidade (FMP).	Função Densidade de Probabilidade (FDP).
Cálculo da Probabilidade	Soma pontual dos pesos de probabilidade.	Área sob a curva (integral) em um intervalo.
Exemplos das Fontes	Número de peças defeituosas em um lote.	Vida útil de máquinas; tempo de espera em filas.

Comportamento da Função de Distribuição Acumulada (FDA)

A FDA, denotada por $F(x) = P(X \le x)$, é o instrumento didático por excelência para visualizar a natureza do fenômeno. Em modelos discretos, a FDA manifesta-se em formato de "degraus", com descontinuidades nos pontos de massa. Em modelos contínuos, a FDA é uma curva suave e ininterrupta, refletindo a transição infinitesimal de probabilidades ao longo do espectro real.

Impacto Analítico ("E daí?"): A falha em distinguir essas naturezas invalida qualquer análise de risco. Modelar o "tempo de vida de uma máquina" (contínuo) como se fosse o "número de falhas" (discreto) ignoraria a natureza densa do tempo, resultando em subestimações críticas de confiabilidade.

3. Teoria de Conjuntos como Gramática da Probabilidade

A teoria de conjuntos fornece a lógica estruturante e a visualização necessária (via Diagramas de Venn) para operacionalizar a chance de múltiplos eventos. No nosso mapeamento direto, o Espaço Amostral equivale ao Conjunto Universo, e os Eventos (simples ou compostos) são Subconjuntos.

Operações, Propriedades e Rigor Matemático

* União ($A \cup B$): Ocorrência de A, de B, ou de ambos.
* Interseção ($A \cap B$): Ocorrência simultânea de A e B.
* Complemento ($A^c$): Ocorrência de tudo o que não pertence a A em S.
* Eventos Mutuamente Excludentes (Disjuntos): Quando $A \cap B = \emptyset$.
* Leis de Morgan: Fundamentais para a simplificação de eventos complementares complexos:  $(A \cup B)^c = A^c \cap B^c (A \cap B)^c = A^c \cup B^c$ 

Partição e o Teorema da Probabilidade Total

Uma Partição de S é um conjunto de eventos $\{A_1, A_2, \dots, A_n\}$ disjuntos e coletivamente exaustivos ($\cup A_i = S$). Esse conceito é o alicerce para o Teorema da Probabilidade Total, que permite decompor a probabilidade de um evento complexo B como a soma das probabilidades condicionais em cada "pedaço" da partição:  $P(B) = \sum_{i=1}^n P(B \cap A_i)$ 

Impacto Analítico ("E daí?"): A visualização via diagramas previne erros lógicos em interseções. Sem o rigor de conjuntos, o analista tende a ignorar as sobreposições, falhando em perceber que a estrutura de uma partição é o que garante que nenhum "peso" de chance seja contado duas vezes ou esquecido.

4. Modelagem Estocástica e a Quantificação da Chance

A transição para a quantificação numérica permite que pesquisadores tomem decisões informadas sob incerteza, substituindo o palpite pelo cálculo de risco calculado.

Abordagens de Cálculo e Limitações

1. Definição Clássica (Laplace): Baseada na equiprobabilidade (todos os resultados têm a mesma chance). $P(A) = \frac{\text{casos favoráveis}}{\text{total de casos}}$. Limitação Crítica: Falha em fenômenos reais onde não há equiprobabilidade, como no peso de pessoas; a chance de alguém pesar entre 60-70kg é drasticamente distinta da faixa 40-50kg, apesar de intervalos idênticos.
2. Definição Frequentista: Estabelece que $P(A)$ é o limite da frequência relativa observada em n repetições independentes quando $n \to \infty$.  $P(A) = \lim_{n \to \infty} \frac{n_A}{n}$ 
3. Axiomas de Kolmogorov: A fundação inegociável da probabilidade moderna. Para qualquer evento A:
  * Não-negatividade: $P(A) \ge 0$.
  * Aditividade: $P(\cup_{i=1}^{\infty} A_i) = \sum_{i=1}^{\infty} P(A_i)$ para eventos disjuntos.
  * Normalização: $P(S) = 1$.

A Esperança Matemática ($E[X]$)

A Esperança Matemática atua como a "média de longo prazo" de um experimento. Ela não representa necessariamente um valor que ocorrerá em uma única rodada, mas sim a média ponderada de todos os resultados possíveis pelos seus respectivos pesos de probabilidade. É a métrica preditiva central para planejamento estratégico e análise de viabilidade.

Regra Geral da Adição

Para evitar a violação do Axioma da Normalização (impedindo que a probabilidade exceda 1), utilizamos a Regra Geral da Adição:  $P(A \cup B) = P(A) + P(B) - P(A \cap B)$  A subtração da interseção é imperativa para evitar a contagem dupla de eventos não-disjuntos.

Impacto Analítico Final: A integração desses pilares — do rigor dos espaços amostrais à flexibilidade dos axiomas — é o que sustenta a ciência de dados e a inferência contemporânea. É esta base que permite definir regiões de rejeição em testes de hipóteses e quantificar o erro, transformando a incerteza de um risco desconhecido em uma variável gerenciável.

### Guia de Estudo: Fundamentos e Modelos de Distribuições de Probabilidade
Este guia foi elaborado sob a perspectiva da psicometria e estatística aplicada para servir como material de referência técnica sobre o arcabouço matemático necessário para a modelagem da incerteza em fenômenos reais.

1. Introdução às Distribuições de Probabilidade

As distribuições de probabilidade constituem a base formal para a análise de fenômenos permeados pela incerteza. Elas permitem que o pesquisador ou arquiteto de dados quantifique a chance relativa de resultados em sistemas complexos, como o tempo de espera em filas ou a estimativa de vida útil de componentes críticos.

•	Definição de Experimento Aleatório: um experimento aleatório é definido pela sua natureza estocástica: ao ser repetido sob as mesmas condições controladas, ele pode fornecer resultados distintos. Essa variabilidade intrínseca é o que demanda o tratamento estatístico.

•	O Modelo Probabilístico em Duas Etapas: a construção do modelo matemático segue um rigoroso processo binário:

o	Etapa 1 (Descrição): Identificação exaustiva do Espaço Amostral (S), garantindo que todos os resultados possíveis sejam previstos e que cada rodada do experimento resulte em apenas um desfecho.

o	Etapa 2 (Atribuição): Atribuição de pesos ou probabilidades aos eventos, definindo a chance de ocorrência de cada ponto ou intervalo do espaço amostral.

•	Classificação dos Espaços Amostrais: A complexidade da análise é ditada pela cardinalidade de S:

o	Modelos Enumeráveis (Finitos ou Infinitos): Lançamentos de moedas ou contagem de falhas.

o	Modelos Não-Enumeráveis: Lançamento de dardos em alvos ou medições físicas, definidos em intervalos contínuos.

A natureza do espaço amostral é o critério primário para a seleção entre modelos discretos ou contínuos. Enquanto o primeiro foca na contagem de eventos, o segundo exige uma abordagem geométrica de mensuração.

2. Distribuições de Probabilidade Discretas

As distribuições discretas operam sobre variáveis cujos resultados podem ser listados ou contados. Para o especialista em psicometria, a lógica central reside na análise combinatória, que funciona como a ferramenta lógica para estruturar o número de caminhos possíveis para um evento de interesse.

Modelo de Bernoulli

Base para experimentos binários únicos.

•	Análise de Parâmetros: O parâmetro p representa a "localização da massa de probabilidade". Em um ensaio de Bernoulli, p é o peso relativo do sucesso.

•	Fórmulas:

o	f.m.p.: $P(X=x) = p^x (1-p)^{1-x}, \text{ para } x \in \{0, 1\}$

o	$E(X) = p$

o	$V(X) = p(1-p)$

Distribuição Binomial

Modela o número de sucessos em n ensaios independentes.

•	Lógica Combinatória: A utilização de combinações de n elementos k a k, \binom{n}{k}, é necessária para determinar o número total de sequências ou caminhos que resultam em exatamente k sucessos. Sem essa técnica de contagem (Aula 5), a probabilidade seria subestimada, pois ignoraria as diferentes ordens de ocorrência.

•	Fórmulas:

o	f.m.p.: $P(X=k) = \binom{n}{k} p^k (1-p)^{n-k}$

o	$E(X) = np$

o	$V(X) = np(1-p)$

Distribuição de Poisson

Aplicada a eventos em "áreas de oportunidade" (tempo ou espaço), como falhas em redes.

•	Análise de Parâmetros: O parâmetro \lambda (taxa média) exerce um peso duplo: ele define tanto o centro quanto a dispersão da distribuição. À medida que \lambda aumenta, a curva tende à simetria, reduzindo sua assimetria (skewness) original.

•	Fórmulas:

o	f.m.p.: $P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!}$

o	$E(X) = \lambda$

o	$V(X) = \lambda$

Distribuição Hipergeométrica

Utilizada em amostragens sem reposição em populações finitas ($N$).

•	Análise Comparativa: O que a distingue da Binomial é o Fator de Correção de População Finita \frac{N-n}{N-1} presente na variância, que reduz a incerteza à medida que a amostra n se aproxima do tamanho total da população.

•	Fórmulas:

o	f.m.p.: $P(X=k) = \frac{\binom{K}{k} \binom{N-K}{n-k}}{\binom{N}{n}}$

o	$E(X) = n \frac{K}{N}$

Diferente dos modelos discretos, onde a probabilidade é atribuída a pontos de massa específicos, a transição para variáveis de mensuração exige uma mudança de paradigma rumo à probabilidade geométrica.

3. Distribuições de Probabilidade Contínuas

Na transição do conceito de contagem para o de mensuração física ou temporal, entramos no domínio da probabilidade geométrica. Aqui, o foco se desloca de pontos para intervalos, pois em espaços não-enumeráveis, a probabilidade de um ponto exato é matematicamente zero.

Uniforme Contínua

Reflete a equiprobabilidade em um intervalo [a, b].

•	Exemplo Geométrico: Em um espaço $S = [0, 10]$, a probabilidade de um evento $A = [1,2] \cup [6,8]$ é calculada pela razão dos comprimentos: $P(A) = \frac{\text{Comprimento de } A}{\text{Comprimento total de } S} = \frac{1 + 2}{10} = 0.3$

•	Fórmulas:

o	f.d.p.: $f(x) = \frac{1}{b-a}$

o	$E(X) = \frac{a+b}{2}$

Distribuição Normal (Gaussiana)

Fundamental para a modelagem de características naturais e psicométricas (como altura).

•	Análise de Parâmetros: A média $\mu$ dita a posição central da "sino" no eixo horizontal, enquanto o desvio padrão $\sigma$ controla o "achatamento" ou a "agudeza" da curva. Um $\sigma$ elevado dispersa a densidade, enquanto um $\sigma$ baixo concentra a probabilidade em torno da média.

•	Normal Padrão ($Z$): Para padronização, utiliza-se $Z = \frac{X - \mu}{\sigma}$, resultando em $E(Z)=0$ e $V(Z)=1$.

Distribuição Exponencial

Modela o tempo de espera ou vida útil. É a contraparte contínua do processo de Poisson.

•	Fórmulas:

o	f.d.p.: $f(x) = \lambda e^{-\lambda x}, \text{ para } x \geq 0$

o	FDA: $F(x) = 1 - e^{-\lambda x}$

o	$E(X) = \frac{1}{\lambda}$

Em modelos contínuos, a probabilidade real é obtida apenas pela integração da função densidade (f.d.p.) sobre um intervalo, representando a área sob a curva. Essa distinção teórica é uma restrição fundamental na arquitetura de dados científicos para variáveis físicas e temporais.

4. Tabela Resumo Comparativa

| Distribuição | Parâmetros | Tipo | Função (f.m.p. ou f.d.p.) | Média $E(X)$ | Variância $V(X)$ |
|--------------|------------|------|----------------------------|--------------|-------------------|
| Bernoulli    | $p$        | D    | $p^x (1-p)^{1-x}$          | $p$          | $p(1-p)$          |
| Binomial     | $n, p$     | D    | $\binom{n}{k} p^k (1-p)^{n-k}$ | $np$     | $np(1-p)$         |
| Poisson      | $\lambda$  | D    | $\frac{e^{-\lambda}\lambda^k}{k!}$ | $\lambda$ | $\lambda$ |
| Hipergeom.   | $N, K, n$  | D    | $\frac{\binom{K}{k}\binom{N-K}{n-k}}{\binom{N}{n}}$ | $n\frac{K}{N}$ | $n\frac{K}{N}\frac{N-K}{N}\frac{N-n}{N-1}$ |
| Uniforme     | $a, b$     | C    | $\frac{1}{b-a}$            | $\frac{a+b}{2}$ | $\frac{(b-a)^2}{12}$ |
| Normal       | $\mu, \sigma$ | C | $\frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}$ | $\mu$ | $\sigma^2$ |
| Exponencial  | $\lambda$  | C    | $\lambda e^{-\lambda x}$   | $\frac{1}{\lambda}$ | $\frac{1}{\lambda^2}$ |



Legenda: D = Discreta; C = Contínua.


## Glossário com os principais conceitos aprendidos

## Conjunto de prompts reutilizáveis que possam apoiar futuras revisões sobre o tema
