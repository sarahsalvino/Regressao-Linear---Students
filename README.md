# Análise do Desempenho de Estudantes de Português

Análise exploratória e modelo preditivo de notas finais de alunos de português em escolas de Portugal, investigando como fatores sociais e acadêmicos influenciam o desempenho escolar.

---

## Objetivo

Entender quais variáveis como consumo de álcool, apoio familiar, reprovações anteriores e tempo de estudo têm maior impacto na nota final (G3) dos alunos, e construir um modelo capaz de prever essa nota.

---

## Estrutura do Projeto

```
 projeto
 ┣ Students_Reorganizado.ipynb   # Notebook principal
 ┣ student-por.csv               # Dataset
 ┗ README.md
```

---

## Dataset

- **Fonte:** [UCI Machine Learning Repository — Student Performance](https://archive.ics.uci.edu/ml/datasets/Student+Performance)
- **649 alunos** | **33 variáveis**
- Dados de alunos da disciplina de português em escolas de Portugal
- Sem valores nulos

### Principais variáveis analisadas

| Variável | Descrição |
|----------|-----------|
| `G1`, `G2` | Notas do 1º e 2º período (0–20) |
| `G3` | **Nota final** — variável alvo |
| `studytime` | Horas de estudo semanais (1–4) |
| `failures` | Reprovações anteriores |
| `absences` | Número de faltas |
| `Dalc` / `Walc` | Consumo de álcool em dias úteis / fim de semana (1–5) |
| `famsup` | Apoio familiar para estudar |
| `goout` | Frequência de sair com amigos (1–5) |
| `Medu` / `Fedu` | Escolaridade da mãe / pai |

---

## Análise Exploratória

### Fatores Sociais investigados
- Diferença de desempenho por **gênero**
- Impacto do **consumo de álcool** (dias úteis vs fim de semana)
- Influência do **apoio familiar** nos estudos
- Efeito de **sair com amigos** e acesso à **internet**
- Comparação entre alunos de zona **urbana e rural**

### Fatores Acadêmicos investigados
- Relação entre **tempo de estudo** e nota final
- Impacto de **reprovações anteriores**
- Influência do número de **faltas**
- Correlação das **notas anteriores** (G1, G2) com G3

---

## Principais Descobertas

- **G2 e G1** são os maiores preditores da nota final (correlação de 0.92 e 0.83)
- **Reprovações anteriores** têm correlação negativa significativa (-0.39)
- **Álcool em dias úteis** prejudica mais do que no fim de semana (-0.21 vs -0.18)
- **Escolaridade dos pais** tem impacto positivo moderado nas notas
- **Tempo de estudo** ajuda, mas de forma moderada (+0.25)

---

## Modelo de Machine Learning

**Algoritmo:** Regressão Linear  
**Features utilizadas:** G1, G2, studytime, failures, absences, Dalc, Walc, goout, famrel  
**Divisão:** 80% treino / 20% teste

### Resultados

| Métrica | Valor |
|---------|-------|
| MAE (Erro Médio Absoluto) | **0.74 pontos** |
| RMSE | **1.15 pontos** |
| R² | **0.8634 (86.3%)** |

O modelo consegue explicar **86,3%** da variação nas notas finais, errando em média apenas **0,74 pontos** numa escala de 0 a 20.

---

## Tecnologias Utilizadas

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

## Como Executar

1. Clone o repositório
```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
```

2. Instale as dependências
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. Abra o notebook
```bash
jupyter notebook Students_Reorganizado.ipynb
```

> Certifique-se de que o arquivo `student-por.csv` está na mesma pasta do notebook antes de rodar.
