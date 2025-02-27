# Car Price Prediction App

## Overview
This is a Flask-based web application that predicts the price of a used car based on various input parameters. The app features a user-friendly UI where users can select car details and get a predicted price.

## Features
- Predicts car prices based on user input.
- Uses a pre-trained Linear Regression model.
- Interactive UI for ease of use.
- API endpoint for predictions.
- CORS enabled for cross-origin access.

## Technologies Used
- Python
- Flask
- Pandas
- NumPy
- Pickle (for model storage)
- HTML, CSS (for UI)
- JavaScript (for frontend interactions)
- Matplotlib & Seaborn (for data visualization)
- Scikit-learn (for model training)

## Installation
1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/car-price-prediction.git
   cd car-price-prediction
   ```
2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
3. Ensure you have the trained model and dataset in place:
   - `Model/LinearRegressionModel.pkl` (Trained Linear Regression model)
   - `Cleaned_Car_data.csv` (Dataset used for fetching car details)

## Running the Application
1. Start the Flask server:
   ```sh
   python app.py
   ```
2. Open your browser and navigate to:
   ```
   http://127.0.0.1:5000/
   ```

## Machine Learning Model
### Data Preprocessing
- Load dataset (`Data.csv`).
- Clean and preprocess data: remove invalid entries, convert data types, and filter outliers.
- Perform exploratory data analysis using Matplotlib and Seaborn.

### Model Training
- Use a Linear Regression model to predict car prices.
- Implement one-hot encoding for categorical features.
- Train-test split applied.
- Optimize model performance using multiple random states.

### Model Evaluation
- Calculate R² score for accuracy.
- Evaluate performance using test data.

### Model Deployment
- Save the trained model using Pickle.
- Load model in Flask app for real-time predictions.

## API Endpoint
### Predict Car Price
- **Endpoint:** `/predict`
- **Method:** POST
- **Request Parameters:**
  - `company`: (string) Car company name
  - `car_models`: (string) Car model name
  - `year`: (int) Manufacturing year
  - `fuel_type`: (string) Type of fuel (Petrol/Diesel/CNG, etc.)
  - `kilo_driven`: (int) Kilometers driven
- **Response:**
  ```json
  {
      "price": 500000.00
  }
  ```
  If there are missing or invalid fields, an error message will be returned.

## File Structure
```
.
|-- Model/
|   |-- LinearRegressionModel.pkl  # Pre-trained model
|
|-- Data/
|   |-- Data.csv  # Raw dataset
|
|-- templates/
|   |-- index.html  # UI Template
|
|-- app.py  # Flask application
|-- Cleaned_Car_data.csv  # Processed dataset
|-- requirements.txt  # Dependencies
```

## Notes
- Ensure that `LinearRegressionModel.pkl` and `Cleaned_Car_data.csv` are in the correct locations.
- Modify `index.html` to customize UI if needed.
- Model performance can be improved by fine-tuning hyperparameters.

## License
This project is open-source and free to use.

## Author
Tanmay Rathod

