# Applied Materials Stock Forecasting with Machine Learning
This project uses Python and machine learning to forecast the next-day stock price of Applied Materials (AMAT) based on historical market trends and technical indicators. It is intended as a professional showcase of applied data science for finance and stock analysis.

---

## 📘 Introduction

The semiconductor industry plays a critical role in powering global innovation, from consumer electronics and AI to industrial automation and renewable energy. Over the past decade, semiconductor equipment manufacturers like **Applied Materials (AMAT)** have experienced significant market growth, driven by rising chip demand, cyclical supply constraints, and rapid advances in fabrication technologies.

Given the high volatility and market sensitivity of semiconductor stocks, this project aims to build a reliable, data-driven model that can forecast the next-day closing price of AMAT using historical price data and technical indicators. By comparing AMAT’s performance with key peers such as **ASML**, **Lam Research (LRCX)**, **KLA (KLAC)**, and the **S&P 500** index, this project aims to better understand market correlations, trends, and predictive patterns that drive price action in this sector.

---

## 🛠️ Technologies Used

- Python 3.x
- Pandas, NumPy
- Scikit-learn
- yfinance
- Seaborn & Matplotlib
- ta (technical analysis library)
- joblib (model saving)

---

## 🔄 Project Workflow

### 1. Data Collection
- Fetched historical stock data (2018–present) for Applied Materials and 4 peer companies (ASML, Lam Research, KLA, and S&P 500) using `yfinance`.

### 2. Exploratory Data Analysis (EDA)
- Visualized price trends and normalized returns to compare long-term performance.
- Analyzed daily return distributions and risk via boxplots and KDE plots.
- Generated correlation heatmaps to explore inter-stock relationships.

### 3. Feature Engineering
- Created features including:
  - Daily percentage returns
  - Moving Averages (MA_5, MA_10, MA_20)
  - Relative Strength Index (RSI)
- Defined the prediction target as the **next-day closing price** (`.shift(-1)`).

### 4. Model Training
- Built and evaluated models to forecast AMAT’s next-day price:
  - Random Forest Regressor
  - Polynomial Linear Regression (**best performer**)

### 5. Evaluation
- Assessed models using RMSE and MAE score.
- Visualized predicted vs. actual prices using line plots and scatterplots with trend lines.

### 6. Model Export
- Saved the final trained model using `joblib` for later reuse or deployment.

---

## 📈 Results & Key Insights

This project produced both actionable modeling results and market insights:

### 📊 Exploratory Data Insights:
- **Strong correlations** (0.85–0.90) between AMAT, KLA, and Lam Research show tight co-movement across the industry.
- **KLA and LRCX** had the highest volatility; **AMAT** showed more stable, consistent growth.
- All semiconductor stocks **outperformed the S&P 500** over the 6-year period, based on normalized growth and cumulative return plots.
- Return distribution plots confirmed that semiconductor stocks carry higher risk but also offer stronger upside potential.

### 🤖 Model Performance:
The **Polynomial Linear Regression model** delivered the strongest results:

- **RMSE:** ~5.4  
  → On average, the model's predictions were within $5.40 of the true closing price.
  
- **Visualizations:**  
  - Line plots show the model closely tracking the actual closing prices over time.  
  - Scatterplots with regression lines confirm low error and stable predictions.

The model was saved as `polynomial_linear_model.pkl` and is ready for future prediction tasks.

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.

---
