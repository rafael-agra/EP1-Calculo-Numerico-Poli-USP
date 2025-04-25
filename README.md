# EP1‑Cálculo Numérico 

Primeiro Exercício Programa (EP1) da disciplina **MAC0210 – Métodos Numéricos** da Escola Politécnica, Universidade de São Paulo. O trabalho aborda **Equações Diferenciais Ordinárias (EDO)** e **aproximação de derivadas** usando métodos de passo simples e passo múltiplo em Python.

## Índice 📑
- Descrição 📝  
- Pré‑requisitos ⚙️  
- Estrutura do Projeto 🗂️  
- Instalação 🔧  
- Uso 🚀  
- Exemplos 💻  
- Funções Disponíveis 🔍  
- Licença 📜  

## Descrição 📝
O repositório contém as seguintes implementações:
- **Método de Euler** (explícito) para resolver EDO de 1ª ordem.  
- **Método de Heun** (Euler melhorado) e **RK4** (Runge–Kutta de 4ª ordem).  
- **Métodos de Adams–Bashforth (AB2, AB3)** e **Adams–Moulton (AM2)** como técnicas de passo múltiplo.  
- **Diferenças finitas** para estimativa de derivadas 1ª e 2ª ordem (progressiva, regressiva, centrada).  
- **Script de comparação de erros** que gera gráficos de log‑log do erro versus passo `h`.  

## Pré‑requisitos ⚙️
- Python ≥ 3.8  
- NumPy e Matplotlib  

## Estrutura do Projeto 🗂️
```
├── euler.py            # Euler simples e melhorado (Heun)
├── runge_kutta.py      # RK4
├── adams.py            # AB2, AB3, AM2
├── finite_diff.py      # Fórmulas de diferenças finitas
├── examples/
│   ├── ode_demo.py     # Demonstra integração de y' = f(x,y)
│   └── error_plot.py   # Gera gráficos de erro log‑log
├── tests/              # Testes unitários
└── LICENSE             # MIT
```

## Instalação 🔧
```bash
git clone https://github.com/rafael-agra/EP1-Calculo-Numerico-Poli-USP.git
cd EP1-Calculo-Numerico-Poli-USP
python -m venv .venv && source .venv/bin/activate  # Linux/macOS
pip install numpy matplotlib
```

## Uso 🚀
Execute um exemplo pronto ou importe as funções:
```bash
python examples/ode_demo.py   # Resolve y' = y - x² + 1
```

Ou no seu script:
```python
from runge_kutta import rk4
f = lambda x, y: y - x**2 + 1
xs, ys = rk4(f, x0=0, y0=0.5, h=0.1, n=10)
```

## Exemplos 💻
### RK4 (h = 0.1)
```
x	aprox	erro
0.0	0.500000	0.000e+00
0.1	0.605170	3.2e‑05
…
```
### Gráfico de erro
Um gráfico log‑log exibirá a inclinação ~4 para RK4, confirmando ordem de convergência.

## Funções Disponíveis 🔍
- `euler(f, x0, y0, h, n)`  
- `heun(f, x0, y0, h, n)`  
- `rk4(f, x0, y0, h, n)`  
- `ab2(f, xs, ys, h)` / `ab3(...)`  
- `am2(f, xs, ys, h)`  
- `forward_diff(f, x, h)` / `backward_diff(...)` / `central_diff(...)`  
Todas incluem docstrings com assinatura completa e exemplos.

## Licença 📜
Distribuído sob a licença **MIT** — consulte o arquivo `LICENSE` para detalhes.

