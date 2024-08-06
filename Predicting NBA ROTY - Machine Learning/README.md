# NBA-Project - Predicting ROTY 

## Overview
Welcome to the NBA Rookie of the Year Prediction project! This project contains all the code and resources required to predict the NBA Rookie of the Year using advanced machine learning techniques. The project leverages historical data from the balldontlie API, spanning from 1979 to the present day. By using this data, we aim to create a robust model that can accurately predict the Rookie of the Year based on various performance metrics and historical trends.

## Data Collection

#### Initial Data Pull

The data collection process begins with pulling historical data from the balldontlie API starting from 1979.  This is done in the notebook First_Pull_Data.ipynb.

#### Daily Data Updates

Data is continually updated using a Glue job scheduled to run at 1 AM daily.
The Glue job checks for new data from the previous day's NBA games, deduplicates, and appends it to the historical dataset.  Refer to Glue Job.ipynb for the Glue job implementation.

## Data Processing
Once the data is collected and stored in Amazon S3, it's processed and transformed into Amazon Redshift for further analysis. Data cleaning and transformation steps are detailed in ROTY Modeling.ipynb.

## Modeling 
The final notebook then trains a machine learning model to predict the NBA Rookie of the Year using the collected and processed data.  Features are engineered using our standardized steps and an SGDClassifier model is found to achieve the best success when training using Scikit-Learn.  The model is capable of predicting the Rookie of the Year for each year using data only from that year, but utilizing all years could lead to increased accuracy.

Achieved accuracy rate: 76%. 

It's worth noting that some of our missed predictions were up for debate in the sports world that year, indicating that our model might be more accurate than the 76% might reflect.


## Libraries Used
Scikit-Learn
Pandas
Numpy
Boto3

## License
This project is licensed under the MIT License.

## Contact
Email: rileysvensson@gmail.com
[LinkedIn Profile](https://www.linkedin.com/in/rileysvensson/)

