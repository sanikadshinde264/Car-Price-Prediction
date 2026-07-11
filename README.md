# Car Price Prediction

A simple Flask web application that predicts the resale price of a used car based on its company, model name, manufacturing year, kilometers driven, and fuel type. Predictions are powered by a scikit-learn Linear Regression pipeline trained on a cleaned used-car dataset.

## Features

- Web form to select car company, model, year, kilometers driven, and fuel type
- Predicts estimated resale price using a trained ML model
- Built with Flask (Python) for the backend and HTML/Jinja2 templates for the frontend

## Tech Stack

- **Python 3**
- **Flask** – web framework
- **pandas / numpy** – data handling
- **scikit-learn** – model pipeline (OneHotEncoder + LinearRegression)

## Project Structure

```
Car Price Prediction/
├── Program1.py                     # Main Flask application
├── cleaned_Data8.csv                # Cleaned dataset used for dropdowns & training
├── LinearRegressionModel.pkl        # Trained scikit-learn pipeline
├── retrain_model.py                 # Script to retrain the model (if needed)
└── templates/
    ├── Home.html
    ├── CarPricePrediction.html
    └── CarPricePredictionResult.html
```

## Setup & Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd "Car Price Prediction"
   ```

2. **Install dependencies**
   ```bash
   pip install flask pandas numpy scikit-learn
   ```
   > If `pip` isn't recognized, use `python -m pip install flask pandas numpy scikit-learn` instead.

3. **Run the app**
   ```bash
   python Program1.py
   ```

4. **Open in browser**
   Navigate to:
   ```
   http://127.0.0.1:5000/
   ```

## Usage

1. Go to the Home page and click through to the prediction form.
2. Select the car's company, model name, year, kilometers driven, and fuel type.
3. Click **Predict** to see the estimated price.

## Retraining the Model

If you get a version-mismatch error (e.g. `AttributeError` related to `OneHotEncoder`), it means the pickled model was trained with a different scikit-learn version than the one installed. Retrain it locally with:

```bash
python retrain_model.py
```

This regenerates `LinearRegressionModel.pkl` using your currently installed scikit-learn version, keeping the same pipeline structure (OneHotEncoder + LinearRegression).

## Notes

- Model accuracy is limited (simple linear regression on a small dataset) — this project is intended as a learning/demo exercise, not a production-grade pricing tool.
- Make sure `cleaned_Data8.csv`, `LinearRegressionModel.pkl`, and the `templates/` folder stay in the same directory as `Program1.py`, since the app uses relative paths.

## License

This project is open source and available for educational use.
