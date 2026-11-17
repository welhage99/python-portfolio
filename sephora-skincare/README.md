# Sephora Skincare Analysis

Exploratory analysis of **2,420 skincare products and over 1 million customer reviews**, translating product and customer data into insights for pricing, assortment, and merchandising decisions.

📓 [View the analysis notebook](Sephora_Skincare_EDA.ipynb)

## Objective

Explore whether premium prices correspond to higher customer ratings, how brands position themselves within skincare categories, and what customer reviews reveal about satisfaction and value.

## Dataset

Source: [Sephora Products and Skincare Reviews — Kaggle](https://www.kaggle.com/datasets/nadyinky/sephora-products-and-skincare-reviews), published by Nady Inky.

- **Product scope:** 2,420 skincare products from an 8,494-product catalog.
- **Reviews:** 1,094,187 records after removing 224 exact duplicates.
- **Coverage:** Reviews available for 97.1% of skincare products.
- **Period:** August 2008 through March 2023.

## Key Findings

| Finding | Evidence | Business relevance |
|---|---|---|
| Higher prices are weakly associated with ratings | Spearman correlation of 0.13 | Price alone provides little guidance on customer satisfaction |
| The assortment concentrates in three categories | Moisturizers, treatments, and cleansers represent 56.9% of products | Evaluate these categories closely, then validate their commercial importance with sales data |
| Premium brands do not consistently earn higher ratings | La Mer and Dr. Barbara Sturm have category-relative price multiples of 4.5× and 3.7×, with average ratings of 4.15 and 4.01 | Investigate whether demand, margin, or brand positioning supports the premium |
| Ratings vary more among products with few reviews | Rating standard deviation of 0.81 for products with 1–10 reviews versus 0.24 above 1,000 | Consider review volume when comparing products |
| Breakout-related language is more common in negative reviews | Appears in 17.9% of 1–2-star reviews versus 13.8% of 4–5-star reviews | Investigate recurring complaints at the product level |

## Analytical Approach

1. **Data acquisition:** Downloaded the dataset through Kaggle’s API and combined five review files.
2. **Cleaning and validation:** Audited missing values, removed exact duplicates, standardized labels, and validated product–review joins.
3. **Exploratory analysis:** Compared category assortment, brand positioning, price distributions, ratings, and engagement.
4. **Feature engineering:** Created category-relative prices, product-label indicators, and scaled numeric features.
5. **Sensitivity analysis:** Examined missing recommendation responses and tested alternative weights for an exploratory product screening index.
6. **Text analysis:** Compared hydration, irritation, breakout, and price mentions across rating groups.
7. **Topic exploration:** Applied Latent Dirichlet Allocation to a reproducible sample of 20,000 reviews.

## Tools

Python · pandas · NumPy · Matplotlib · seaborn · scikit-learn · requests · Jupyter Notebook

## Business Takeaways

- Compare ratings alongside review counts.
- Review products with substantial price premiums and average or below-average ratings.
- Use review themes to identify products needing further investigation.
- Report recommendation rates with response coverage.
- Validate product shortlists against sales, margin, returns, and category strategy before acting.

## How to Run

Install the required packages:

    pip install jupyter pandas numpy matplotlib seaborn scikit-learn requests

Launch Jupyter:

    jupyter notebook

Open `Sephora_Skincare_EDA.ipynb` and run the cells in order.

The notebook downloads `sephora_data.zip` on its first run and reuses the saved archive afterward. Initial execution requires internet access.

## Limitations

This is a historical, descriptive analysis. Reviews are self-selected, and platform engagement does not measure sales or profitability. Keyword matching cannot fully interpret context or negation. Prices are not standardized by package size, and observed relationships do not establish causation.

## Project Context

Completed as a group academic project.
