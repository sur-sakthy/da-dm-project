# Data Mining Project: Forecasting In-Patient & Day Case Waiting Time
The aim of this project is to forecast the number of patients in each time-band. We made use of the historical data 
provided by [The National Treatment Purchase Fund](https://data.gov.ie/dataset/ipdc-waiting-list-by-group-hospital).

The patients in the waiting list are grouped in one of these categories:
- 0-3 months
- 3-6 months
- 6-9 months
- 9-12 months
- 12-15 months
- 15-18 months
- 18+ months

Models implemented in this project:
- ARIMA (AutoRegressive Integrated Moving Average)
- SARIMA (Seasonal AutoRegressive Integrated Moving Average)
- TBATS (Trigonometric seasonality, Box-Cox transformation, ARMA errors, Trend and Seasonal components)
- Facebook/Meta Prophet

The results obtained from running those models can be observed in the [report](report/"Forecasting In-Patient Waiting Times.pdf") as well as the .ipynb files (runnable in 
Google Colab).

## Jupyter Notebooks
1. [merging_data_2014_2021.ipynb](merging_data_2014_2021.ipynb)
   - Dataset columns renamed: column headers between 2017 to 2021 were unaligned and needed cleaning to be done. 
   - The separate .csv files are merged into one .csv file.
   - The merged .csv file is named [merged.csv](merged.csv) which can be found in the root folder of the repo.

2. [eda_and_modelling.ipynb](eda_and_modelling.ipynb)
   - Loaded in merged dataset: data between 2014 and 2021 (March)
   - Checked for missing data
   - Extracted out the relevant data from the dataset - column _**count**_ 
   - Aggregated the data per month
   - Basic data visualisation - moving average, exponential smoothing, ETSD (Error Trend Seasonality Decomposition)
   - ADF (Augmented Dickey-Fuller) statistical test
   - Split dataset into train and test sets
   - Implementation of ARIMA - plotted and evaluated
   - Implementation of SARIMA - plotted and evaluated
   - Implementation of TBATS - plotted and evaluated
   - Implementation of Prophet - plotted and evaluated
