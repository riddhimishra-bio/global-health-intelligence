# Global Health Intelligence
### Exploring Global Health Indicators Through Data Analytics (2015–2023)

An exploratory data analysis project investigating relationships between life expectancy, infant mortality and healthcare expenditure across countries using publicly available World Bank data.

## Project Overview

Health outcomes differ considerably across countries. Understanding how indicators such as life expectancy, infant mortality and healthcare expenditure vary can help identify important patterns in global public health.

This project uses Python-based data analysis to explore these relationships over the period 2015–2023.

**Research question:** What relationships exist between healthcare expenditure, infant mortality and life expectancy across countries?

## Objectives

- Examine life expectancy trends between 2015 and 2023.
- Investigate the relationship between life expectancy and infant mortality.
- Explore the association between healthcare expenditure and health outcomes.
- Compare changes in life expectancy between 2019 and 2021.
- Identify missing data and unusual observations.

## Dataset

**Source:** World Bank Open Data  
https://data.worldbank.org/topic/health

Three indicators were retrieved using the World Bank API:

| Indicator | World Bank code |
|---|---|
| Life expectancy at birth | SP.DYN.LE00.IN |
| Infant mortality rate | SP.DYN.IMRT.IN |
| Current health expenditure (% of GDP) | SH.XPD.CHEX.GD.ZS |

**Study period:** 2015–2023

**Geographical coverage:** 217 countries and territories in the filtered dataset.

The initial merged dataset contained 2,349 country-year observations. Five observations with life expectancy below 40 years were flagged for investigation and excluded from the main exploratory analysis, leaving 1,948 observations.

## Tools and Technologies

- Python
- Pandas
- Requests
- Plotly
- Google Colab
- GitHub

## Methodology

1. Retrieved health indicator records from the World Bank API.
2. Combined the three datasets using country codes and year.
3. Filtered regional aggregates using World Bank country metadata.
4. Examined missing values and unusual life expectancy observations.
5. Performed exploratory data analysis.
6. Calculated Pearson and Spearman correlation coefficients.
7. Compared life expectancy in 2019 and 2021 for countries with observations in both years.
8. Created interactive visualisations using Plotly.

## Key Findings

### 1. Correlation analysis

| Indicator relationship | Pearson | Spearman |
|---|---:|---:|
| Life expectancy vs infant mortality | -0.904 | -0.921 |
| Life expectancy vs health expenditure | 0.249 | 0.360 |
| Infant mortality vs health expenditure | -0.270 | -0.426 |

The strongest observed relationship was between life expectancy and infant mortality, with a strong negative correlation.

Healthcare expenditure as a percentage of GDP showed weaker associations with both health outcomes.

### 2. Life expectancy changes (2019–2021)

Among 216 countries with observations in both years, the mean country-level change in life expectancy was -1.277 years.

Countries with the largest reported decreases included:

- Bolivia: -6.393 years
- Paraguay: -5.560 years
- Mexico: -4.780 years
- Guyana: -4.744 years
- Peru: -4.679 years

The largest reported increases included:

- Syrian Arab Republic: +1.448 years
- Republic of Congo: +1.040 years
- Samoa: +0.827 years
- Sierra Leone: +0.667 years
- Mongolia: +0.592 years

These are unweighted averages of country-level changes, not population-weighted global estimates.

## Data Quality and Limitations

- Infant mortality and health expenditure contained missing observations.
- Five life expectancy observations below 40 years were flagged and excluded from the main exploratory analysis pending further investigation.
- Correlations are descriptive associations and do not establish causality.
- Country-year observations are repeated measurements and should not be treated as fully independent.
- Healthcare expenditure as a percentage of GDP does not directly measure healthcare access, efficiency or quality.
- Changes in country coverage and reporting can influence annual comparisons.

## Repository Structure

```text
global-health-intelligence/
│
├── data/
│   ├── global_health_analysis.csv
│   └── life_expectancy_2019_2021_comparison.csv
│
├── notebooks/
│   └── Global_Health_Intelligence.ipynb
│
├── visualizations/
│   └── life_expectancy_country_comparison.html
│
├── README.md
└── LICENSE
```

## Reproducibility

The analysis was conducted using Google Colab.

To reproduce the analysis:

1. Open the notebook in Google Colab.
2. Run the cells sequentially.
3. Retrieve the indicator data through the World Bank API.
4. Execute the data-cleaning and analysis steps.
5. Generate the visualisations.

## Future Scope

- Incorporate additional socioeconomic and healthcare access indicators.
- Investigate country-specific trends.
- Apply population-weighted analysis.
- Explore multivariable statistical models.
- Develop an interactive public-health analytics dashboard.

## Author

**Independent Health Data Analytics Project**

Developed as a practical exploration of Python, statistical analysis and public-health data.

**Data source:** World Bank Open Data.

