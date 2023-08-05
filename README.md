# AssetTracker
Aqui está a documentação do seu código na sintaxe do GitHub:

```markdown
# Rastreador de Ações usando yfinance

Este é um script Python que utiliza a biblioteca `yfinance` para baixar dados de ações da bolsa de valores e plotar gráficos de preços.

## Instalação

Antes de executar o script, você precisa instalar a biblioteca `yfinance`. Você pode fazer isso executando o seguinte comando:

```bash
!pip install yfinance --quiet
```

## Importações

O script requer as seguintes bibliotecas para funcionar:

```python
import yfinance as yf
import matplotlib.pyplot as plt
```

Certifique-se de que essas bibliotecas estejam instaladas antes de executar o script.

## Definição dos Tickers

Os tickers das ações que você deseja rastrear são definidos na lista `tickers`. Por exemplo:

```python
tickers = ['AAPL', 'MSFT', 'PETR4.SA', 'BBDC4.SA']
```

## Baixar Dados

Os dados das ações são baixados usando a função `yf.download()`. Aqui está um exemplo de como os dados são baixados:

```python
dados_tickers = yf.download(tickers, period='id', start='2022-01-01')
```

## Plotagem de Gráficos

### Gráfico de Preços

O script cria um gráfico de linhas mostrando os preços ajustados (`Adj Close`) das ações. O código para plotar o gráfico é o seguinte:

```python
dados_tickers['Adj Close'].plot()
plt.xlabel('Data')
plt.ylabel('Preço')
plt.title('Rastreador de Ações')
plt.legend(fontsize=7)
plt.show()
```

### Gráfico Normalizado

Além do gráfico de preços, o script também cria um gráfico normalizado, que mostra a variação percentual dos preços em relação ao primeiro dia. O código para plotar o gráfico normalizado é o seguinte:

```python
dados_tickers_normalizados = dados_tickers['Adj Close'] / dados_tickers['Adj Close'].iloc[0]
dados_tickers_normalizados.plot()
plt.xlabel('Data')
plt.ylabel('Preço')
plt.title('Rastreador de Ações - Normalizado')
plt.legend(fontsize=7)
plt.show()
```

## Executando o Script

Após instalar as bibliotecas necessárias e ajustar os tickers conforme desejado, você pode executar o script para baixar os dados e plotar os gráficos de preços das ações.

Certifique-se de ter todas as dependências instaladas e, em seguida, execute o script em um ambiente Python compatível.
