# Transformer Encoder from Scratch — IMDB Sentiment Classification

> **Natural Language Processing and Applications | Shoeb Shakil Sutar | PRN: 25070149022**

## Overview

This repository contains the implementation for the research paper:

**"Building a Transformer Encoder from Scratch: A Comparative Evaluation Against Classical Machine Learning Models for Sentiment Classification"**

The core idea of this project is **not** to achieve state-of-the-art accuracy. The goal is to understand how a Transformer Encoder works by building it entirely from scratch in PyTorch — without any pre-training, transfer learning, or borrowed weights — and observe what it can learn purely from the task data.

The model is compared against four classical ML baselines (Logistic Regression, Naïve Bayes, Random Forest, Linear SVC) under realistic conditions.

---

## Repository Structure

```
transformer-imdb-sentiment/
│
├── IMDB_Transformer_Encoder.ipynb     # Transformer built from scratch
├── IMDB_Traditional_ML.ipynb          # Classical ML baselines
├── requirements.txt                   # Dependencies
└── README.md
```

---

## Model Architecture

The Transformer Encoder is built completely from scratch:

| Component | Details |
|-----------|---------|
| Hidden Size | 256 |
| Attention Heads | 8 |
| Encoder Layers | 4 |
| FFN Size | 1024 |
| Max Sequence Length | 256 |
| Dropout | 0.1 |
| Normalization | Pre-Layer Normalization |
| Optimizer | Adam (lr = 1e-4) |
| Loss | CrossEntropyLoss |
| Epochs | 50 |

---

## Results Summary

| Model | Feature | Test Accuracy | Macro F1 |
|-------|---------|--------------|---------|
| **Transformer Encoder** | Raw Tokens | **86%** | **0.86** |
| Logistic Regression | TF-IDF | 88% | 0.88 |
| Logistic Regression | Count | 87% | 0.87 |
| Linear SVC | TF-IDF | 88% | 0.88 |
| Linear SVC | Count | 86% | 0.86 |
| Multinomial NB | Count | 85% | 0.85 |
| Random Forest | Count | 84% | 0.84 |
| Random Forest | TF-IDF | 84% | 0.84 |

---

## Dataset

IMDB Large Movie Review Dataset — Maas et al. (2011)
- 50,000 reviews (25,000 train / 25,000 test)
- Binary labels: positive / negative
- Download: https://ai.stanford.edu/~amaas/data/sentiment/

---

## How to Run

### Option 1 — Google Colab (Recommended)
1. Open the notebook in Colab
2. Upload the IMDB dataset CSV
3. Run all cells top to bottom

### Option 2 — Local
```bash
git clone https://github.com/YOUR_USERNAME/transformer-imdb-sentiment.git
cd transformer-imdb-sentiment
pip install -r requirements.txt
jupyter notebook
```

---

## Requirements

See `requirements.txt`

---

## Citation

If you use this code, please cite:

```
Sutar, S.S. (2025). Building a Transformer Encoder from Scratch: 
A Comparative Evaluation Against Classical Machine Learning Models 
for Sentiment Classification. M.Tech Project, Symbiosis Institute of Technology, Pune.
```
