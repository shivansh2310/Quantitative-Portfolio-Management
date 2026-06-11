# Quantitative Portfolio Management: Statistical Arbitrage Sprint

This repository contains a 7-day guided implementation of the architectures described in **"Quantitative Portfolio Management: The Art and Science of Statistical Arbitrage"** by Michael Isichenko.

Moving beyond fundamental factor models, this project constructs a complete **Statistical Arbitrage (StatArb)** pipeline. It focuses on large-scale data engineering, machine learning-driven alpha generation, signal ensembling, noise-filtering via Random Matrix Theory, and handling the mathematical realities of market impact and transaction costs.

## 🛠️ Tech Stack
* **Language:** Python
* **Environment:** Jupyter Notebooks / Google Colab
* **Key Libraries:** `pandas`, `numpy`, `scikit-learn` (Linear Models, PCA), `xgboost` / `lightgbm` (Non-linear ML), `scipy.optimize`, `statsmodels`

## 📅 The 7-Day StatArb Architecture

Each folder contains a standalone Colab notebook translating Isichenko's theoretical frameworks into vectorized, production-ready Python code.

| Day | Core Concept | Implementation Project |
| :--- | :--- | :--- |
| **Day 1: Data Pipelines & Targets** | Feature engineering, Survivorship bias, The Idiosyncratic Target. | Building a cross-sectional neutralization pipeline to strip market/sector beta and generate "pure" residual return targets. |
| **Day 2: Linear Alpha & Regularization** | Momentum, Mean-reversion, Bias-Variance tradeoff, Curse of dimensionality. | Training penalized regressions (Ridge/Lasso) across standardized historical features to generate baseline linear forecasts. |
| **Day 3: Non-Linear Alpha (ML)** | Conditional interactions, Tree-based ensembles, Feature importance. | Implementing an XGBoost regressor to capture non-linear alpha, focusing on managing the extreme noise-to-signal ratio of financial data. |
| **Day 4: Risk & Random Matrix Theory** | The Marchenko-Pastur distribution, Eigenvalue clipping, PCA risk models. | Engineering a covariance filter using Random Matrix Theory (RMT) to mathematically separate structural risk from statistical noise. |
| **Day 5: The Cost of Trading** | Slippage, Almgren-Chriss market impact, Square-root impact laws. | Building a transaction cost simulator that dynamically penalizes theoretical returns based on volume, volatility, and execution speed. |
| **Day 6: Constrained Optimization** | Alpha blending, Mean-Variance with friction, Position sizing. | Building a convex optimizer that balances our blended ML alpha forecasts against our RMT risk model and non-linear trading costs. |
| **Day 7: Purged Cross-Validation** | Serial correlation, Data leakage, Out-of-sample Sharpe estimation. | Replacing standard K-Fold CV with Purged and Embargoed Cross-Validation to generate statistically robust, trustable backtest metrics. |

## 🚀 How to Use This Repository

This repository is designed as a sequential pipeline. To explore the concepts:
1. Navigate to the respective Day's folder.
2. Open the `.ipynb` file.
3. Click the **"Open in Colab"** badge at the top of the notebook (if configured) or run locally.
4. Run the cells sequentially. *Note: Days 5-7 rely on the outputs and models generated in Days 1-4.*

## 🧠 Core Philosophy
> *"The overarching principle of quantitative trading is that the signal-to-noise ratio is very low."* This project does not attempt to find a "magic formula." Instead, it focuses on the rigorous mathematical defense against noise: neutralizing targets, regularizing models, clipping covariance matrices, penalizing turnover, and purging backtests.

## 📖 Reference
* Isichenko, Michael. *Quantitative Portfolio Management: The Art and Science of Statistical Arbitrage*. Wiley, 2021.
