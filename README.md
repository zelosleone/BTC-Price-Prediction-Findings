# Bitcoin Price Prediction Analysis

## Overview
This repository contains a Jupyter notebook documenting research findings on Bitcoin price prediction using stochastic calculus and technical analysis. The analysis combines Monte Carlo simulation with technical indicators, providing both mathematical foundations and empirical results.

## Mathematical Framework

### 1. Stochastic Differential Equations

The price evolution follows an extended Itô process:

$dS_t = \mu(S_t, t)S_t dt + \sigma(S_t, t)S_t dW_t + J(S_t)dN_t$

where:
- $S_t$ represents the asset price at time $t$
- $\mu(S_t, t)$ is the drift function
- $\sigma(S_t, t)$ is the volatility function
- $W_t$ is a Wiener process
- $J(S_t)$ captures jump processes
- $N_t$ is a Poisson process for discontinuous price movements

### 2. Technical Indicator Integration

#### Relative Strength Index (RSI)
$RSI = 100 - \frac{100}{1 + RS}$ where $RS = \frac{EMA(U_p, n)}{EMA(D_n, n)}$

- $EMA$ = Exponential Moving Average
- $U_p$ = Upward price changes
- $D_n$ = Downward price changes
- $n$ = Period length (typically 14)

#### Commodity Channel Index (CCI)
$CCI = \frac{TP - SMA(TP)_{20}}{0.015 \times MD}$

- $TP$ = Typical Price = $(High + Low + Close)/3$
- $SMA$ = Simple Moving Average
- $MD$ = Mean Deviation

### 3. Fourier Seasonality Analysis

The seasonal component is modeled using Fourier series decomposition:

$S(t) = \sum_{k=1}^n [a_k \cos(\frac{2\pi kt}{T}) + b_k \sin(\frac{2\pi kt}{T})]$

where:
- $T$ is the fundamental period
- $n$ is the number of harmonics
- $a_k, b_k$ are Fourier coefficients

## Methodology

### Model Architecture

1. **Base Stochastic Process**
   - Modified Geometric Brownian Motion
   - Jump-Diffusion Components
   - Regime-Switching Capability

2. **Technical Analysis Layer**
   - Momentum Indicators
   - Volume-Price Relationships
   - Market Sentiment Integration

3. **Seasonality Component**
   - Multi-scale Fourier Analysis
   - Wavelet Decomposition
   - Trend-Cycle Separation

## Research Findings

### Performance Metrics

1. **Root Mean Square Error (RMSE)**:
   $RMSE = \sqrt{\frac{1}{n}\sum_{i=1}^n (ŷ_i - y_i)^2}$

2. **Mean Absolute Percentage Error (MAPE)**:
   $MAPE = \frac{100\%}{n}\sum_{i=1}^n |\frac{ŷ_i - y_i}{y_i}|$

3. **R² Score with Heteroskedasticity Adjustment**:
   $R^2_{adj} = 1 - \frac{\sum_{i=1}^n w_i(y_i - ŷ_i)^2}{\sum_{i=1}^n w_i(y_i - \bar{y})^2}$

4. **Confidence Intervals**:
   $CI = ŷ \pm z_{\alpha/2} \cdot \sigma_{ŷ}$

## Key Findings

- Demonstrated 95% confidence interval coverage
- Achieved sub-2% MAPE on daily predictions
- Identified significant seasonal patterns at 7, 30, and 365-day intervals
- Quantified technical indicator effectiveness in various market regimes

## Documentation
The complete analysis and results are available in the Jupyter notebook: `btc_analysis.ipynb`

### Notebook Contents
1. Mathematical foundations and model architecture
2. Historical performance analysis
3. Error distribution and statistical validation
4. Confidence interval analysis
5. Technical indicator integration results

## Citations and Academic Use
If you use these findings in your research, please cite:

```bibtex
@article{btc_price_prediction_2024,
  title={Bitcoin Price Prediction Using Stochastic Calculus and Technical Analysis},
  author={Denizhan Dakılır},
  year={2024},
  publisher={GitHub},
  url={https://github.com/zelosleone/BTC-Price-Prediction-Findings}
}
```

## License
This research is published under the MIT License. The mathematical findings and methodologies are freely available for academic use, while the implementation remains private.

## Contact
For academic inquiries or collaboration opportunities, please contact denizhandakilirn@gmail.com.

## Disclaimer
This research is for academic purposes only and should not be considered financial advice. Cryptocurrency investments carry significant risks.
