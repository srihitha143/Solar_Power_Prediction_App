☀️ Solar Power Generation Prediction

📌 Project Overview

This project is a **Regression-based Machine Learning application** designed to predict solar energy output (measured in Joules per 3-hour period). By analyzing environmental factors like temperature, humidity, and sky cover, the model provides accurate forecasts to help optimize grid management and renewable energy distribution.

The project includes a full **Exploratory Data Analysis (EDA)** pipeline and a **Futuristic Radar-themed Dashboard** built with Streamlit for real-time predictions.

🚀 Live Dashboard Features

  * **Real-time Prediction:** Input weather variables via a sidebar to get instant power output estimates.
  * **Radar UI:** A custom-styled "Futuristic Radar" interface with CSS animations.
  * **Comparative Analytics:** Visualizes how your predicted power compares against historical maximums.
  * **Interactive Controls:** Sliders and dropdowns for Sky Cover (0-4 scale), Visibility, and more.

📊 Dataset Description

The model is trained on `solarpowergeneration.csv`, containing 2,920 instances and 10 environmental variables:

  * **distance\_to\_solar\_noon:** Solar position in radians.
  * **sky\_cover:** 5-step scale (0 = Clear, 4 = Overcast).
  * **temperature:** Daily average in Celsius.
  * **humidity:** Moisture percentage.
  * **visibility:** Atmospheric clarity in km.
  * **wind\_speed:** Average speed in m/s.

🛠️ Machine Learning Pipeline

1\. Data Preprocessing & EDA

  * **Missing Values:** Handled via mean imputation for `average-wind-speed-(period)`.
  * **Feature Selection:** Through correlation analysis, redundant features like `wind_direction` and `average_pressure_period` were dropped to reduce noise.
  * **Standardization:** Used `StandardScaler` to normalize feature magnitudes.

2\. Model Performance

After testing Linear, Ridge, Lasso, and Ensemble models, **XGBoost** was selected as the champion model.

| Model | MAE | RMSE | **R² Score** |
| :--- | :--- | :--- | :--- |
| Linear Regression | \~3900 | \~5300 | 0.61 |
| **XGBoost (Tuned)** | **\~1600** | **\~3300** | **0.90** |

3\. Key Insights

  * **Strongest Predictors:** `distance_to_solar_noon` and `sky_cover` show the highest negative correlation with power output.
  * **Accuracy:** The model achieves a high R² score of 0.90, explaining 90% of the variance in solar energy production.

💻 Installation & Setup

1.  **Clone the repo:**

    ```bash
    git clone https://github.com/your-username/solar-power-prediction.git
    cd solar-power-prediction
    ```

2.  **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the EDA/Model Training:**

    ```bash
    python spg_model.py
    ```

4.  **Launch the Streamlit App:**

    ```bash
    streamlit run app.py
    ```

📂 Project Structure

  * `spg_model.py`: Comprehensive EDA, feature engineering, and model training script.
  * `app.py`: Streamlit application file with custom CSS styling.
  * `model.pkl` & `scaler.pkl`: Serialized model and scaler for deployment.
  * `solarpowergeneration.csv`: The raw dataset used for training.

project done by :Nakka Srihitha
