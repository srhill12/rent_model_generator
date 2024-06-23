# Rent Prediction Model for Texas and California

This project involves training a rent prediction model for Texas and California using housing data. The project utilizes a custom module, `pipeline_utilities`, to generate and evaluate the models.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Project Steps](#project-steps)
  - [Data Import](#data-import)
  - [Model Training](#model-training)
  - [Model Evaluation](#model-evaluation)
- [Results](#results)

## Installation

1. Install the required packages:
pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score
import pandas as pd
from sklearn.preprocessing import StandardScaler, OneHotEncoder
from sklearn.pipeline import Pipeline
from sklearn.linear_model import LinearRegression

## Usage

To run the project, follow these steps:

1. Import the necessary modules and data.
2. Train the models for Texas and California.
3. Evaluate the model performance.

## Project Steps

### Data Import

1. **Import the Data**: Load the rent data for Texas and California into Pandas DataFrames.
    ```python
    import pandas as pd

    # Import the data
    rent_tx_df = pd.read_csv("https://static.bc-edx.com/ai/ail-v-1-0/m12/lesson_3/datasets/rent_data_tx.csv")
    rent_ca_df = pd.read_csv("https://static.bc-edx.com/ai/ail-v-1-0/m12/lesson_3/datasets/rent_data_ca.csv")

    # Look at the first few rows of the California data
    rent_ca_df.head()
    ```

### Model Training

2. **Import Custom Module**: Import the `pipeline_utilities` module.
    ```python
    import pipeline_utilities as p_utils
    ```

3. **Train the Model for Texas**: Use the `rent_model_generator` function from the custom module.
    ```python
    tx_model = p_utils.rent_model_generator(rent_tx_df)
    ```

4. **Train the Model for California**: Use the `rent_model_generator` function from the custom module.
    ```python
    ca_model = p_utils.rent_model_generator(rent_ca_df)
    ```

### Model Evaluation

Evaluate the models based on the output from the `rent_model_generator` function. The function provides metrics such as Mean Squared Error (MSE), R-squared, and Adjusted R-squared.

## Results

### Texas Model
- **Dropped 73.58% rows**
- **Testing with dropped NAs**:
  - Mean Squared Error: 72936.54
  - R-squared: 0.39
  - Adjusted R-squared: 0.25
- **Testing without dropping data**:
  - Mean Squared Error: 86395.29
  - R-squared: 0.41
  - Adjusted R-squared: 0.38

### California Model
- **Dropped 82.51% rows**
- **Testing with dropped NAs**:
  - Mean Squared Error: 1270465.61
  - R-squared: 0.11
  - Adjusted R-squared: -0.83
- **Testing without dropping data**:
  - Mean Squared Error: 1331543.10
  - R-squared: 0.38
  - Adjusted R-squared: 0.32

The results indicate that the model performance varies significantly between Texas and California, with the Texas model showing better overall performance.

## Reference

UC Irvine Machine Learning Repository. 2019. *Apartment for rent classified* [Dataset]. Available: https://archive.ics.uci.edu/dataset/555/apartment+for+rent+classified [2023, August 24]. ([CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/legalcode))

