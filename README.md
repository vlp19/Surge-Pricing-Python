# Surge-Price-Estimation
This project analyzes and predicts rideshare fare volatility in the New York City metropolitan area. Using a dataset of over 1 million trips, I developed a gradient-boosted regression model (LightGBM), as well as linear regression models, to estimate fares and utilized SHAP to deconstruct what goes on behind the scenes of surge pricing.

The goal was to move beyond traditional linear pricing models to understand the interaction effects—the specific thresholds where distance, time, and location compound to create exponential price spikes.


📊 **Key Findings**
The 20/30 Threshold: Surge prices are primarily driven by two physical tipping points: trips exceeding 20 miles or durations exceeding 30 minutes. Beyond these marks, prices increase exponentially rather than linearly.

The Anchor vs. The Nudge: Trip Distance is the dominant predictor (SHAP impact up to $140), while temporal factors like "Hour of Day" and "Day of Week" act as minor "nudges" (SHAP impact ±$3), despite common consumer perception that time-of-day is the primary driver.

Model Bias: The model maintains a +11% over-prediction mode, prioritizing revenue stability and driver compensation in a high-volatility urban market.

🛠️ **Tech Stack**
Modeling: LightGBM (Gradient Boosting Regression)

Explainability: SHAP (Beeswarm, Waterfall, and Dependence plots)

Data Handling: Pandas, NumPy, PyArrow (Parquet processing)

Visualization: Matplotlib

📈 **Model Performance**
The model was evaluated using MAPE (Mean Absolute Percentage Error) to ensure accuracy across both short-haul and long-haul trip profiles.

Mode Error: +11%

Primary Error Bin: -20% to +42%

Feature Importance: Validated through both native LightGBM gain metrics and SHAP global importance rankings.

💡 **Business Logic: "What Could Happen Next"**
The project concludes with a strategic framework for Dynamic Margin Optimization:

1. GIS-Informed Location Premiums: Integrating geographic data to identify high-affluence corridors where price elasticity is lower.

2. Inelastic Demand Windows: Identifying "lack of alternative" windows for commuters to optimize margins without significant volume loss.

3. Subscription Modeling: Using SHAP volatility profiles to price "Surge Shield" subscriptions for high-frequency users.

📂 Repository Structure
Plaintext
├── data/                   # Parquet files (NYC FHV Trip Data)
├── notebooks/              # Surge_Price_Estimation.ipynb
├── images/                 # SHAP and Performance plots
├── src/                    # Custom MAPE and utility functions
└── README.md

🚀 **How to Use**
Clone the repo: git clone *https://github.com/yourusername/surge-price-estimation.git*

Install dependencies: pip install -r requirements.txt

Run the Jupyter Notebook to see the step-by-step SHAP deconstruction of NYC fares.

**Author- Vincent Piper**
