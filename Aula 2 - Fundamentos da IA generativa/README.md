# Aula 2 - Fundamentos da IA Generativa

Este repositório reúne notebooks da disciplina com exemplos práticos de IA/Deep Learning usando `TensorFlow/Keras`.

## Conteúdo do projeto

- `Aula 2 - Fundamentos da IA generativa/Criando um modelo com embeddings.ipynb`
- `Aula 2 - Fundamentos da IA generativa/Rede Neural Multilayer Perceptron.ipynb`
- `Aula 2 - Fundamentos da IA generativa/Redes Neurais Convolucionais - Classificando cães e gatos.ipynb`
- `Aula 2 - Fundamentos da IA generativa/Redes Neurais Recorrentes - Escrevendo um novo capítulo como Lewis Carroll.ipynb`
- `Aula 2 - Fundamentos da IA generativa/wonderland.txt` (base textual para o notebook de RNN)
- `Aula 2 - Fundamentos da IA generativa/training_checkpoints/` (pesos salvos durante treino)
- `Aula 2 - Fundamentos da IA generativa/SementesAbobora.xlsx`
- `requirements.txt`

## Pré-requisitos

- Python 3.10+ (recomendado)
- `pip`
- VS Code com extensão Jupyter **ou** Jupyter Lab/Notebook instalado

## Como executar localmente

No diretório raiz do projeto:

```bash
python -m venv .venv
source .venv/Scripts/activate  # Git Bash no Windows
# .venv\Scripts\activate      # PowerShell/CMD

pip install --upgrade pip
pip install -r requirements.txt
```

Depois, abra os notebooks com VS Code (Jupyter) ou execute:

```bash
jupyter lab
```

## Ordem sugerida de estudo

1. `Criando um modelo com embeddings.ipynb`
2. `Rede Neural Multilayer Perceptron.ipynb`
3. `Redes Neurais Convolucionais - Classificando cães e gatos.ipynb`
4. `Redes Neurais Recorrentes - Escrevendo um novo capítulo como Lewis Carroll.ipynb`

## Execução no Google Colab

1. Faça upload do notebook desejado.
2. Garanta que os arquivos auxiliares estejam disponíveis no ambiente (`wonderland.txt`, etc.).
3. Instale as dependências necessárias no início do notebook, se preciso:

```python
!pip install -q tensorflow keras numpy pandas matplotlib seaborn scikit-learn gensim nltk tqdm opencv-python
```

4. Se houver inconsistência entre CPU e GPU, teste o runtime em `CPU` para validar se o problema é de compatibilidade do ambiente.

## Notas importantes

- A pasta `training_checkpoints/` está ignorada no Git (`.gitignore`) para evitar versionamento de pesos temporários.
- Ao alterar versões de `tensorflow/keras` no Colab, reinicie o runtime antes de continuar.

## Solução de problemas (RNN no Colab)

Se ocorrer erro durante `fit()` com GRU/LSTM:

- Reinicie o runtime e execute o notebook do início.
- Evite misturar `keras` e `tf.keras` no mesmo notebook.
- Prefira uma implementação simples/estável para treino em graph mode.

Exemplo de compile para diagnóstico:

```python
model.compile(optimizer="adam", loss=loss, run_eagerly=True)
```

Se funcionar com `run_eagerly=True`, o problema tende a ser de tracing/graph mode no ambiente atual.
