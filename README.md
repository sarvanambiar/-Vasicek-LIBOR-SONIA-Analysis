# Modeling the Vasicek Framework for LIBOR and SONIA

This repository contains the implementation and results of a group project titled **"Modeling the Vasicek Framework for LIBOR and SONIA: Analyzing Structural Differences and Volatility Dynamics."** The project applies the Vasicek interest rate model to analyze and compare the dynamics of LIBOR and SONIA, focusing on structural differences, volatility, and implications for financial markets.

## Overview

### Key Objectives
- Analyze historical data (1997–2024) for LIBOR and SONIA.
- Estimate Vasicek model parameters using Maximum Likelihood Estimation (MLE).
- Forecast interest rates and compare them with actual values.
- Highlight anomalies in LIBOR related to manipulation.

### Project Highlights
- SONIA aligns closely with Vasicek model assumptions due to its transaction-based, risk-free nature.
- LIBOR shows greater volatility and anomalies, reflecting potential manipulation during 2005–2012.
- The Vasicek model demonstrates robustness in forecasting SONIA compared to LIBOR.

## Methodology

1. **Data Collection**:
   - **SONIA**: Retrieved from the Bank of England.
   - **LIBOR**: Sourced from Bloomberg.
   - Dataset spans January 1997 to March 2024.

2. **Model Description**:
   - The Vasicek model is represented by the stochastic differential equation:
     ```
     dr(t) = a \cdot (b - r(t)) \cdot dt + \sigma \cdot dW(t)
     ```
     - `a`: Speed of mean reversion.
     - `b`: Long-term mean.
     - `\sigma`: Volatility.
     - `dW(t)`: Wiener process representing random fluctuations.

3. **Implementation**:
   - MATLAB was used for data processing, parameter estimation, and forecasting.
   - The `fmincon` function was utilized for Maximum Likelihood Estimation (MLE).

4. **Evaluation**:
   - Root Mean Squared Error (RMSE) was used to assess forecasting accuracy.
   - Visualizations include time-series plots, histograms, and density estimates.

## Results

The results and detailed analysis are documented in the **`results/Project_Report.pdf`**. Key findings include:

### Vasicek Model Parameters
| Metric         | SONIA   | LIBOR   |
|----------------|---------|---------|
| Speed of Mean Reversion (`a`) | 1.0517 | 0.0361 |
| Long-term Mean (`b`) | 2.6904 | 1.7271 |
| Volatility (`\sigma`) | 3.5071 | 0.4220 |

### Forecast Accuracy
| Metric | SONIA | LIBOR |
|--------|-------|-------|
| RMSE   | 3.064 | 2.696 |

## Repository Structure

- **`data/`**: Contains SONIA and LIBOR datasets in `.csv` and `.xlsx` formats.
- **`scripts/`**: MATLAB scripts for data preprocessing, parameter estimation, and forecasting.
- **`results/`**:
  - **Graphs**: Plots of actual vs. forecasted rates, histograms, and density estimates.
  - **`Project_Report.pdf`**: Full report with detailed explanations and findings.

## How to Run

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/vasicek-libor-sonia.git
   ```
2. **Set up MATLAB**:
   Open MATLAB and navigate to the `scripts/` directory.
3. **Run the scripts**:
   - Run `estimate_vasicek_mle.m` for parameter estimation.
   - Run `forecast_rates.m` to generate forecasts.
   - Visualize results using the provided plotting scripts.
4. **View outputs**:
   - Results, including plots and RMSE values, are saved in the `results/` directory.

## Dependencies

- MATLAB (tested with R2023a or later)
- Required MATLAB toolboxes:
  - Optimization Toolbox
  - Statistics and Machine Learning Toolbox

## Limitations and Future Work

### Limitations
- The Vasicek model assumes constant parameters, which may not fully capture market dynamics.
- The model does not account for exogenous variables, such as central bank policies or macroeconomic shocks.

### Future Work
- Extend the model to incorporate features of CIR, Hull-White, or multi-factor models.
- Include stochastic volatility and regime-switching features to improve accuracy.
- Expand datasets to include additional global benchmarks for broader comparisons.

## Authors

This project was developed by:
- **Hoang Lan Anh Nguyen**
- **Sarvamangala Nambiar**
- **Tejas Manjunath**
- **Yash Gokhale**
- **Malhar Kaustubh Mardikar**

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

---
