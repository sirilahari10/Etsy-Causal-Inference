# 🛒 Marketplace Causal Inference: Does Seller Effort Actually Drive Sales?

*Bridging user intent with marketplace growth through rigorous experimentation and causal thinking.*

## The Context
In a two-sided marketplace like Etsy, product teams constantly encourage sellers to optimize their listings. But how do we know which optimizations *actually* work? 

This project explores a classic "messy" product question: **Does writing a longer product description cause higher sales, or do successful sellers simply write longer descriptions because they have more resources?**

## The "Messy" Reality 
If we just look at averages, items with long descriptions sell more. But correlation is not causation. Heavier, more expensive, or more complex items naturally require longer descriptions *and* have different baseline conversion rates. If we just tell all sellers to write 500+ words without proving causality, we waste their time and erode trust in our seller tools.

## The Methodology: Propensity Score Matching & IPW
Instead of a basic A/B test simulation, this project uses **Observational Causal Inference** to isolate the true impact of description length.

1. **The Data:** Modeled using the Olist E-Commerce dataset (100k+ anonymized marketplace orders).
2. **Propensity Scoring:** I used Logistic Regression to calculate the probability (propensity) that an item receives a long description based on its physical confounders (weight, photo count).
3. **Inverse Probability Weighting (IPW):** I re-weighted the dataset to mathematically balance the "treated" (long description) and "control" (short description) groups.
4. **Weighted Least Squares (WLS):** I calculated the true causal uplift of the description length on the probability of becoming a top-selling item.

## 📊 The Business Takeaway
By controlling for confounding variables, the model revealed a **statistically significant causal uplift**. 

* **Impact:** Writing a description of >500 characters directly increases the probability of high sales volume. 
* **Product Recommendation:** We should actively invest in UI features (like LLM-assisted drafting or progress bars) that prompt sellers to hit this character count, knowing it will causally improve their marketplace success.

---
*Built with Python, Pandas, Statsmodels, and Scikit-Learn.*
