# Fandango Movie Rating Analysis: Investigating Systemic Inflation

## Project Summary
This data science project investigates the common claim that **Fandango systematically inflates its displayed "Star" ratings** for movies. The analysis compares Fandango's internal rating systems against critic and user scores from major platforms, including **Rotten Tomatoes, Metacritic, and IMDB**, to quantify any discrepancies and validate the inflation hypothesis.

---

## 🎯 Project Goal

The primary objective was to perform a rigorous statistical analysis to:
1.  Quantify the difference between Fandango's publicly **Displayed STARS** (the 0-5 stars shown on the site) and its true internal **Actual RATING** (the score calculated from user reviews).
2.  Compare the normalized score distributions across Fandango, Rotten Tomatoes, and Metacritic to understand platform-specific rating biases.

---

## 📈 Key Findings & Results

The analysis successfully validated the rating inflation claim with quantifiable results derived from statistical comparisons and data visualization:

| Finding | Metric | Key Insight |
| :--- | :--- | :--- |
| **Quantified Inflation** | Average `STARS_DIFF` = **0.47** | Fandango's displayed star rating is, on average, **0.47 stars higher** than its true calculated rating. |
| **Most Common Bias** | Mode `STARS_DIFF` = **0.5** | The most frequent discrepancy observed was a half-star (0.5) inflation. |
| **Distribution Skew** | Heavy bias towards 4.0-5.0 | Fandango's score distribution is significantly skewed toward the high end of the scale, whereas critic scores (Metacritic/Rotten Tomatoes) show a much more critical and spread-out distribution. |
| **Highest Mean Score** | Fandango's scores | Fandango has the highest average rating among all compared platforms, even when normalized to the same 0-5 scale. |

***Conclusion:*** This analysis confirms that Fandango's rating system presents a systematically **inflated view** of a movie's quality compared to other major review sites.

---

## ⚙️ Methodology & Technical Skills

### Data Preparation and Feature Engineering
* **Data Cleaning:** Extracted release year from movie titles and handled erroneous data points.
* **Normalization:** Implemented a crucial step to standardize all ratings to a common **0-5 scale** for a fair, direct comparison across all platforms (e.g., converting Rotten Tomatoes' 0-100 scale and IMDB's 0-10 scale).
* **Core Metric Creation:** Engineered the `STARS_DIFF` column (`Displayed STARS - Actual RATING`) to serve as the core metric for quantifying inflation.

### Analysis & Visualization
* Utilized **Kernel Density Estimation (KDE) plots** to visually compare the distribution differences of normalized ratings across all platforms.
* Employed **Count Plots** to visualize the frequency of the `STARS_DIFF` metric, clearly showing that 0.5 is the most common difference.
* Used Descriptive Statistics to calculate mean, median, and mode for all rating columns to statistically confirm the inflation and distribution bias.

---

## 🛠️ Technologies Used

* **Language:** Python
* **Core Libraries:** `Pandas`, `NumPy`
* **Visualization:** `Matplotlib`, `Seaborn`

---

## 📂 Repository Structure

* [`Capstone.ipynb`](Capstone.ipynb): The full Jupyter Notebook containing all the analysis, code, visualizations, and conclusions.
* `fandango_scrape.csv, all_site_scores.csv`: The primary datasets used for this analysis.
