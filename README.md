# Online Shopping Clickstream Analytics using Python

Exploratory data analysis of the UCI clickstream dataset for online clothing shopping (e-shop clothing 2008), covering 165,474 clicks across April-August 2008.

## Objective

Understand how visitors browse an online clothing store: what they click on, when, from where, and how price and page layout relate to browsing depth.

## Dataset

- Source: UCI "Clickstream data for online shopping" (`e-shop-clothing-2008.csv`, `;` separated)
- 165,474 rows, 14 columns: date, click order within the session, country, session ID, product category, clothing model, colour, photo location on page, photography style, price, above-average price flag, page number
- Date range: 2008-04-01 to 2008-08-13

## Approach

- **Data understanding:** structure, data types and summary statistics
- **Cleaning and validation:** column renaming, code-to-label mapping (category, colour, location, country, photography), date construction, and consistency checks
- **Univariate analysis:** clicks by category, colour, weekday and country; histograms of price, click order and page number
- **Bivariate and multivariate analysis:** box plots, bar charts, scatter plot of price against click order
- **Correlation analysis:** correlation heatmap, category-by-location heatmap, violin plot of price by photography style
- **Outlier analysis:** box plots of price and click order
- **Time series:** daily click volume

## Key Findings

- No missing values or duplicate rows; every product model has one consistent price
- Poland accounts for about 81% of clicks, followed by the Czech Republic
- Trousers are the most clicked category; black and blue are the most clicked colours
- Traffic peaks Tuesday-Wednesday and is lowest on Saturday
- Daily traffic fell sharply after an early-April peak and then stayed fairly stable
- Price has a weak negative correlation with page number (-0.15): cheaper items tend to appear on later pages
- Click order is heavily right-skewed (median 6, maximum 195): a few very long sessions

## Repository Structure

```
eshop-clickstream-analytics/
├── project1.ipynb
├── e-shop-clothing-2008.csv
├── report.docx
└── README.md
```

## How to Run

1. Install the requirements: `pip install numpy pandas matplotlib seaborn scipy jupyter`
2. Update the path in the `pd.read_csv(...)` cell to where the CSV is stored on your machine (the notebook currently uses a local Windows path)
3. Run: `jupyter notebook project1.ipynb` and execute all cells

## Limitations

- Clickstream data has no purchase or conversion outcome, so findings describe browsing behaviour only
- One shop, one season and a single dominant country (Poland)
- Findings are descriptive and do not establish causation
