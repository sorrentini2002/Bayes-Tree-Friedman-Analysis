## Overview
This project explores the comparative performance of classifiers and the effectiveness of the Friedman test in different settings. It consists of three distinct parts, each addressing a theoretical or practical aspect of binary classification and statistical testing. The project includes simulations, Monte Carlo studies, and real-world data analysis.

The main objectives are:
1. Compare decision tree and Bayes classifier performance on simulated data.
2. Analyze the power and size of the Friedman test with logistic regression.
3. Apply the methodology to real-world heart rate data to classify effort zones.

## Prerequisites
To run this project, you will need the following software and R packages:

### Software
- **R Programming Language** (version 4.0 or higher)

### R Packages
- `rpart`, `MASS`, `ggplot2`, `pROC`, `broom`, `kableExtra`

To install the required R packages, run:

```r
install.packages(c("rpart", "MASS", "ggplot2", "pROC", "broom", "kableExtra"))
```

## Project Structure

### Part 1: Decision Tree vs. Bayes Classifier

**Objective**: Compare the performance of a decision tree classifier and a theoretical Bayes classifier on simulated overlapping uniform distributions.

* **Steps**:

  1. **Data Generation**: Generate a dataset with `n = 1000` observations.
  2. **Bayes Classifier**: Derive and evaluate the theoretical Bayes classifier.
  3. **Decision Tree Tuning**: Tune the decision tree using validation sets to optimize performance.
  4. **Monte Carlo Simulation**: Run a simulation with `M = 10,000` iterations to evaluate classifier stability and accuracy.

* **Results**: The decision tree slightly outperformed the Bayes classifier in terms of mean accuracy and stability, mainly due to its flexibility in capturing underlying patterns in the data.

---

### Part 2: Friedman Test for Logistic Regression

**Objective**: Evaluate the size and power of the Friedman test when applied to logistic regression across different parameter settings (sample size, feature dimensionality, and distribution distance).

* **Steps**:

  1. **Data Generation**: Generate data from multivariate normal distributions.
  2. **Friedman Test Implementation**: Implement the Friedman test with logistic regression and permutation-based significance testing.
  3. **Power Analysis**: Analyze the test's power for different effect sizes (`delta = 0.3`, `delta = 0.5`), sample sizes, and feature dimensions.

* **Results**: The Friedman test's power was found to increase with sample size and effect size (`delta`). However, higher feature dimensionality (`k`) reduced the test's power when the effect size was small.

---

### Part 3: Application to Heart Rate Data

**Objective**: Use logistic regression and the Friedman test to classify effort zones (Zone-2, Zone-3, Zone-4) based on heart rate data (speed and altitude features).

* **Steps**:

  1. **Feature Engineering**: Compute relevant features such as mean speed and elevation gain.
  2. **Model Training**: Train a logistic regression model and simplify it to make the model more interpretable.
  3. **Friedman Test**: Use the Friedman test to compare score distributions between different zones.
  4. **Evaluation**: Use ROC curve analysis to assess model performance and compare zones pairwise.

* **Results**: Significant differences were observed between all effort zones. The model achieved an AUC of 0.85 for the comparison between Zone-2 and Zone-3.

---

## How to Run

1. **Data Preparation**:
   Ensure the file `hw_data.RData` is located in your working directory. This file is required for Part 3 but is not included due to privacy concerns.

2. **Execute the Analysis**:
   Open the RMarkdown file `Grillo_Querqui_Sorrentini.Rmd` in RStudio and click the "Knit" button to generate the HTML report. Make sure all dependencies are installed before running the analysis.

---

## Key Findings

1. **Part 1**: Decision trees can outperform theoretically optimal classifiers in practical scenarios due to their flexibility in handling complex data patterns.
2. **Part 2**: The Friedman test's power is influenced by sample size, effect size, and the number of features. Larger sample sizes and effect sizes increase power, while higher dimensionality may decrease it.
3. **Part 3**: Engineered features such as speed variability and elevation gain are crucial for distinguishing effort zones in real-world heart rate data. The logistic regression model achieved an AUC of 0.85 for Zone-2 vs. Zone-3.

---

## Notes

* The `hw_data.RData` file for Part 3 is not included in the repository due to privacy restrictions.
* To speed up testing and exploration, you can adjust the number of Monte Carlo iterations (`M`) in the code.

---

## Authors

* **Emidio Grillo**
* **Alessandro Querqui**
* **Matteo Sorrentini**

---

## License

This project is licensed under the MIT License.

