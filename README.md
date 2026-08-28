# Phishing Email Detection

A phishing email classifier comparing custom word embeddings against traditional bag-of-words features across several machine learning models.

## Overview

Trained and evaluated multiple classifiers on cleaned email text, testing whether **custom CBOW (Continuous Bag-of-Words) embeddings** offer an advantage over classical **bag-of-words** representations for phishing detection.

## Results

| Model | Features | Accuracy |
|---|---|---|
| **MLP (best model)** | CBOW embeddings | **96%** |
| Random Forest | CBOW embeddings | 93% |
| Decision Tree, SVC, Naive Bayes | Bag-of-words (baseline) | — |

The MLP trained on CBOW embeddings outperformed all bag-of-words baselines and the Random Forest comparison model, showing that learned embeddings captured more useful structure in email text than sparse count-based features for this task.

## Approach

1. **Preprocessing**: email text cleaning and tokenisation.
2. **Baseline models**: Decision Tree, SVC, and Naive Bayes trained on bag-of-words features.
3. **Primary models**: custom CBOW embeddings generated from the cleaned corpus, used to train and compare an MLP against a Random Forest.
4. **Evaluation**: accuracy comparison across all models to identify the best-performing feature/model combination.

## Project structure

```
PhishingDet/
├── Phishing Detection.ipynb   # full pipeline: preprocessing, baselines, primary models
├── emails_cleaned.csv         # preprocessed dataset used for testing
├── word_embeddings.txt        # CBOW embeddings generated for the primary models
├── Robert Pauls - Report.pdf  # write-up of methodology and findings
```

## Running it

1. Run the **Load Packages** and **Mount Google Drive** cells.
2. For baseline models: run **Tokenisation**, then **Baseline Models**.
3. For primary models: run **Primary Models** (uses the provided dataset and embeddings to generate and evaluate the test sets).

## Tech stack

Python, PyTorch, scikit-learn, NLTK.
