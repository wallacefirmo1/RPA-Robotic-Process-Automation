# RPA-Robotic-Process-Automation

RPA - Robotic Process Automation - Enviar um e-mail TODOS OS DIAS com análise das cotações de algumas ações

## APLICAÇÃO E RESULTADO DO CÓDIGO ABAIXO (ASSISTA O VÍDEO)

![RPA - ROBOTIC PROCESS AUTOMATION](https://github.com/wallacefirmo1/RPA-Robotic-Process-Automation/assets/146641541/43123e25-66a9-47c3-a791-27ab414d426f) (https://drive.google.com/file/d/1KNBJLYroN10Y00vJNOn4fxqsEV5k1U9h)

### APERTE NA IMAGEM PARA SER REDIRECIONADO PARA O VÍDEO

## CENÁRIO

#### Você trabalha em uma empresa de investimentos.

## OBJETIVO

#### Enviar um e-mail TODOS OS DIAS com análise das cotações de algumas ações


```python
# RPA Robozinho
```

# SEU TRABALHO

    *Entrar no Yahoo Finance
    *Selecionar ação
    *Selecionar o período
    *Fazer download
    *Montar análises
    *Preparar e-mail
    *Enviar e-mail
    
Tempo estimado: 2 horas
    

# DEPOIS DO PYTHON

    *Rodar o sistema
    *Escolher a ação
    
#### Tempo estimado: 10 segundos


```python
# Bibliotecas sáo os super poderes do Python

# A solução para QUALQUER problema que você queira resolver

# http://python.org
```


```python
!pip install yfinance
```

    Requirement already satisfied: yfinance in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (0.2.31)
    Requirement already satisfied: peewee>=3.16.2 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (3.17.0)
    Requirement already satisfied: frozendict>=2.3.4 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (2.3.8)
    Requirement already satisfied: requests>=2.31 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (2.31.0)
    Requirement already satisfied: pytz>=2022.5 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (2023.3.post1)
    Requirement already satisfied: beautifulsoup4>=4.11.1 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (4.11.1)
    Requirement already satisfied: numpy>=1.16.5 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (1.21.5)
    Requirement already satisfied: pandas>=1.3.0 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (1.4.4)
    Requirement already satisfied: html5lib>=1.1 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (1.1)
    Requirement already satisfied: lxml>=4.9.1 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (4.9.1)
    Requirement already satisfied: multitasking>=0.0.7 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (0.0.11)
    Requirement already satisfied: appdirs>=1.4.4 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from yfinance) (1.4.4)
    Requirement already satisfied: soupsieve>1.2 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from beautifulsoup4>=4.11.1->yfinance) (2.3.1)
    Requirement already satisfied: webencodings in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from html5lib>=1.1->yfinance) (0.5.1)
    Requirement already satisfied: six>=1.9 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from html5lib>=1.1->yfinance) (1.16.0)
    Requirement already satisfied: python-dateutil>=2.8.1 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pandas>=1.3.0->yfinance) (2.8.2)
    Requirement already satisfied: idna<4,>=2.5 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from requests>=2.31->yfinance) (3.3)
    Requirement already satisfied: charset-normalizer<4,>=2 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from requests>=2.31->yfinance) (2.0.4)
    Requirement already satisfied: certifi>=2017.4.17 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from requests>=2.31->yfinance) (2022.9.24)
    Requirement already satisfied: urllib3<3,>=1.21.1 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from requests>=2.31->yfinance) (1.26.11)



```python
!pip install pyautogui
```

    Requirement already satisfied: pyautogui in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (0.9.54)
    Requirement already satisfied: pyobjc-core in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyautogui) (10.0)
    Requirement already satisfied: mouseinfo in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyautogui) (0.1.3)
    Requirement already satisfied: pytweening>=1.0.4 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyautogui) (1.0.7)
    Requirement already satisfied: pyobjc-framework-quartz in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyautogui) (10.0)
    Requirement already satisfied: pygetwindow>=0.0.5 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyautogui) (0.0.9)
    Requirement already satisfied: pymsgbox in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyautogui) (1.0.9)
    Requirement already satisfied: pyscreeze>=0.1.21 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyautogui) (0.1.29)
    Requirement already satisfied: pyrect in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pygetwindow>=0.0.5->pyautogui) (0.2.0)
    Requirement already satisfied: pyscreenshot in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyscreeze>=0.1.21->pyautogui) (3.1)
    Requirement already satisfied: Pillow>=9.2.0 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyscreeze>=0.1.21->pyautogui) (9.2.0)
    Requirement already satisfied: rubicon-objc in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from mouseinfo->pyautogui) (0.4.7)
    Requirement already satisfied: pyperclip in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from mouseinfo->pyautogui) (1.8.2)
    Requirement already satisfied: pyobjc-framework-Cocoa>=10.0 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyobjc-framework-quartz->pyautogui) (10.0)
    Requirement already satisfied: entrypoint2 in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyscreenshot->pyscreeze>=0.1.21->pyautogui) (1.1)
    Requirement already satisfied: mss in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyscreenshot->pyscreeze>=0.1.21->pyautogui) (9.0.1)
    Requirement already satisfied: EasyProcess in /Users/wallacefirmo/opt/anaconda3/lib/python3.9/site-packages (from pyscreenshot->pyscreeze>=0.1.21->pyautogui) (1.1)


# Instalar vs Usar

##### Instalar, só usa UMA VEZ. Usar sempre que for usar, implicito no seu código.

# Problema a ser resolvido

- Buscar de forma automática informações de ações da bolsa de valores;
- Criar as análises solicitada pelo Gestor;
- Enviar automaticamente um email com os resultados das análises.


```python
# Bibliotecas ( Yahoo Finance ) !pip install yfinance
# Bibliotecas ( Pyautogui ) !pip install pyautogui
# Bibliotecas ( Pyperclip ) !pip install pyperclip
```

# Buscar informações de ações


```python
import yfinance
```


```python
ticker = input("Digite o código da ação: ")

yfinance.Ticker(ticker)
```

    Digite o código da ação: PETR4.SA





    yfinance.Ticker object <PETR4.SA>




```python
# Buscando pelo periodo de 6 meses (6mo)

codigo = input("Digite o código da ação: ")

yfinance.Ticker(codigo).history("6mo")
```

    Digite o código da ação: PETR4.SA





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Dividends</th>
      <th>Stock Splits</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2023-05-15 00:00:00-03:00</th>
      <td>23.560272</td>
      <td>23.641639</td>
      <td>22.963580</td>
      <td>23.198641</td>
      <td>81996700</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-05-16 00:00:00-03:00</th>
      <td>23.605477</td>
      <td>24.437229</td>
      <td>23.578354</td>
      <td>23.777250</td>
      <td>117782700</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-05-17 00:00:00-03:00</th>
      <td>24.048475</td>
      <td>24.193127</td>
      <td>23.063029</td>
      <td>23.198641</td>
      <td>107129200</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-05-18 00:00:00-03:00</th>
      <td>23.135357</td>
      <td>23.370417</td>
      <td>22.918378</td>
      <td>23.334253</td>
      <td>63010500</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-05-19 00:00:00-03:00</th>
      <td>23.578354</td>
      <td>23.668762</td>
      <td>23.180559</td>
      <td>23.298090</td>
      <td>69245500</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2023-11-08 00:00:00-03:00</th>
      <td>34.599998</td>
      <td>34.799999</td>
      <td>33.910000</td>
      <td>34.169998</td>
      <td>59742900</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-11-09 00:00:00-03:00</th>
      <td>34.500000</td>
      <td>35.150002</td>
      <td>34.360001</td>
      <td>34.880001</td>
      <td>56231100</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-11-10 00:00:00-03:00</th>
      <td>34.660000</td>
      <td>35.060001</td>
      <td>34.509998</td>
      <td>34.720001</td>
      <td>40004800</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-11-13 00:00:00-03:00</th>
      <td>34.680000</td>
      <td>35.750000</td>
      <td>34.669998</td>
      <td>35.689999</td>
      <td>44120000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-11-14 00:00:00-03:00</th>
      <td>35.689999</td>
      <td>36.090000</td>
      <td>35.490002</td>
      <td>36.060001</td>
      <td>37259100</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>128 rows × 7 columns</p>
</div>




```python
# Gravar no Sistema

codigo = input("Digite o código da ação: ")

tabela_dados = yfinance.Ticker(codigo).history("6mo")
```

    Digite o código da ação: PETR4.SA



```python
acao = "PETR4.SA"
```


```python
# Como acessar dados especificos da tabela

tabela_dados.Open
```




    Date
    2023-05-15 00:00:00-03:00    23.560272
    2023-05-16 00:00:00-03:00    23.605477
    2023-05-17 00:00:00-03:00    24.048475
    2023-05-18 00:00:00-03:00    23.135357
    2023-05-19 00:00:00-03:00    23.578354
                                   ...    
    2023-11-08 00:00:00-03:00    34.599998
    2023-11-09 00:00:00-03:00    34.500000
    2023-11-10 00:00:00-03:00    34.660000
    2023-11-13 00:00:00-03:00    34.680000
    2023-11-14 00:00:00-03:00    35.689999
    Name: Open, Length: 128, dtype: float64




```python
tabela_dados
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Dividends</th>
      <th>Stock Splits</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2023-05-15 00:00:00-03:00</th>
      <td>23.560272</td>
      <td>23.641639</td>
      <td>22.963580</td>
      <td>23.198641</td>
      <td>81996700</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-05-16 00:00:00-03:00</th>
      <td>23.605477</td>
      <td>24.437229</td>
      <td>23.578354</td>
      <td>23.777250</td>
      <td>117782700</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-05-17 00:00:00-03:00</th>
      <td>24.048475</td>
      <td>24.193127</td>
      <td>23.063029</td>
      <td>23.198641</td>
      <td>107129200</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-05-18 00:00:00-03:00</th>
      <td>23.135357</td>
      <td>23.370417</td>
      <td>22.918378</td>
      <td>23.334253</td>
      <td>63010500</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-05-19 00:00:00-03:00</th>
      <td>23.578354</td>
      <td>23.668762</td>
      <td>23.180559</td>
      <td>23.298090</td>
      <td>69245500</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2023-11-08 00:00:00-03:00</th>
      <td>34.599998</td>
      <td>34.799999</td>
      <td>33.910000</td>
      <td>34.169998</td>
      <td>59742900</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-11-09 00:00:00-03:00</th>
      <td>34.500000</td>
      <td>35.150002</td>
      <td>34.360001</td>
      <td>34.880001</td>
      <td>56231100</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-11-10 00:00:00-03:00</th>
      <td>34.660000</td>
      <td>35.060001</td>
      <td>34.509998</td>
      <td>34.720001</td>
      <td>40004800</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-11-13 00:00:00-03:00</th>
      <td>34.680000</td>
      <td>35.750000</td>
      <td>34.669998</td>
      <td>35.689999</td>
      <td>44120000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-11-14 00:00:00-03:00</th>
      <td>35.689999</td>
      <td>36.090000</td>
      <td>35.490002</td>
      <td>36.049999</td>
      <td>37260700</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>128 rows × 7 columns</p>
</div>



```python

# Como Criar o gráfico no python ( Código "plot")

tabela_dados.plot()
```


    <AxesSubplot:xlabel='Date'>




    
![download](https://github.com/wallacefirmo1/RPA-Robotic-Process-Automation/assets/146641541/14638774-275c-4b59-b299-5f33bd905762)
    



```python
tabela_dados.Close
```




    Date
    2023-05-15 00:00:00-03:00    23.198641
    2023-05-16 00:00:00-03:00    23.777250
    2023-05-17 00:00:00-03:00    23.198641
    2023-05-18 00:00:00-03:00    23.334253
    2023-05-19 00:00:00-03:00    23.298090
                                   ...    
    2023-11-08 00:00:00-03:00    34.169998
    2023-11-09 00:00:00-03:00    34.880001
    2023-11-10 00:00:00-03:00    34.720001
    2023-11-13 00:00:00-03:00    35.689999
    2023-11-14 00:00:00-03:00    36.049999
    Name: Close, Length: 128, dtype: float64




```python
fechamento = tabela_dados.Close
```


```python
fechamento.hist()
```




    <AxesSubplot:>


    
![Imagem 2](https://github.com/wallacefirmo1/RPA-Robotic-Process-Automation/assets/146641541/e076670b-a79c-413e-8cd6-4715bf44fadf)



```python
tabela_dados.hist()
```




    array([[<AxesSubplot:title={'center':'Open'}>,
            <AxesSubplot:title={'center':'High'}>,
            <AxesSubplot:title={'center':'Low'}>],
           [<AxesSubplot:title={'center':'Close'}>,
            <AxesSubplot:title={'center':'Volume'}>,
            <AxesSubplot:title={'center':'Dividends'}>],
           [<AxesSubplot:title={'center':'Stock Splits'}>, <AxesSubplot:>,
            <AxesSubplot:>]], dtype=object)



![Imagem 3](https://github.com/wallacefirmo1/RPA-Robotic-Process-Automation/assets/146641541/0e1e1735-c318-4bf4-a04e-c8a86fed0cc2)

    


# Gerar análises

- 6 meses
- Cotação máxima
- Cotação minima
- Cotação atual


```python
# Varrer o maximo

maximo = round(fechamento.max(),1)
```


```python
# Varrer o maximo

minimo = round(fechamento.min(),1)
```


```python
# Acessando o indice por cada dia ( Lembrando que cada dia começa por 0 )

maximo
```




    38.5




```python
# Como acessar a ultima linha ( -1 entre [])

maximo[-1]
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /var/folders/st/g3zqnqsx2qj8kgwg02c_fhtr0000gn/T/ipykernel_5446/1166359921.py in <module>
          1 # Como acessar a ultima linha ( -1 entre [])
          2 
    ----> 3 maximo[-1]
    

    TypeError: 'float' object is not subscriptable



```python
fechamento = tabela_dados.Close
```


```python
# Como arredondar para um numero legivel ( usando a "round"+ , numero (1) casas decimais)

round(fechamento[-1], 1)
```




    36.0



# Enviar e-mail automaticamente

- abrir uma nova aba (CTRL + T ou Command + T )
- digitar o endereço do Gmail
- clicar enter
- clicar no botão escrever
- preencher o destinatário (contato@wallacefirmo.com )
- clicar no TAB (passar para proxima coluna)
- preencher o assunto
- clicar no TAB (passa para corpo do email)
- preencher o corpo do email
- clicar no botão enviar



```python
import pyautogui
import pyperclip
```


```python
# configurar o Pyautogui para dar uma pausa de 2 segundos entre as passadas

pyautogui.PAUSE = 3

# abrir uma nova aba (command + t)

pyautogui.hotkey("command", "t")

# digitar o endereço do Gmail
pyperclip.copy("http://gmail.com")
pyautogui.hotkey("command", "v")

# clicar no enter

pyautogui.hotkey("enter")

# clicar no botão Escrever

time.sleep(3)
pyautogui.click(x=77, y=219)

# preencher email ao destinatário (Clicar em Tab)

time.sleep(4)
pyperclip.copy("contato@wallacefirmo.com, firmo.wallace2@gmail.com")
pyautogui.hotkey("command", "v")
pyautogui.hotkey("tab")

# preencher assunto (clicar em tab)

time.sleep(4)
pyperclip.copy(f"Análise de Dados: Cotação Petrobras - {codigo}")
pyautogui.hotkey("command", "v")
pyautogui.hotkey("tab")

# preencher corpo do email

mensagem_cotacao = f"""
Prezado Wallace Firmo, 

Seguem as análises diárias da ação: {codigo} referente aos últimos seis meses:

Cotação máxima: R${maximo}
Cotação miníma: R${minimo}

Qualquer dúvida fico à disposição!

"""

time.sleep(4)
pyperclip.copy(mensagem_cotacao)
pyautogui.hotkey("command", "v")

# clicar no botão Enviar

time.sleep(8)
pyautogui.click(x=730, y=773)



```


```python
# Como programar o python para aguardar eu abrir a tela do GMAIL para pegar a posição

import time

time.sleep(2)
print("Wallace")
```

    Wallace



```python
time.sleep(5)
pyautogui.position()
```




    Point(x=468, y=405)



# FRASE DO DIA

### Estou vivendo a minha melhor experiencia de aprendizado
