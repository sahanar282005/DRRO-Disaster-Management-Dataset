
```markdown
# DRRO: Multimodal Disaster Relief and Resource Optimization Dataset

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Field: Disaster Management](https://img.shields.io/badge/Field-Disaster%20Management-red.svg)]()

## Overview
This repository contains the official multimodal datasets used in the research paper: **"DRRO: AI Based System for Real Time Disaster Relief and Resource Management."** The DRRO framework bridges the gap between chaos and coordination by integrating image-based detection, SMS-enabled emergency communication, and ML-driven resource allocation. Because synchronized multimodal data from real-world disasters is exceptionally scarce and restricted by privacy laws, we curated and synthesized this composite dataset to support research reproducibility.

## Dataset Architecture

The dataset is organized into three core modules, reflecting the interdependent nature of the DRRO framework:

```text
DRRO-Dataset/
│
├── Image_Data/                 # Spatial Imagery for CNN Training
│   ├── Earthquake/             # ~500 images of structural damage
│   ├── Fire/                   # ~500 images of wildfire/urban fire
│   └── Flood/                  # ~500 images of inundated areas
│
├── SMS_Data/                   # NLP Corpus for Urgency Classification
│   └── synthetic_sms_corpus.csv # 4-tier categorized distress signals
│
└── Resource_Allocation_Data/   # Logistical Training Data
    └── simulated_logistics.csv  # Severity-to-Supply mapping

```

### 1. Spatial Image Dataset

* **Source:** Manually aggregated from public web repositories and filtered for high relevance.
* **Categories:** Flood, Fire, and Earthquake.
* **Preprocessing:** Images standardized to $224 \times 224$ pixels.
* **Purpose:** Training the Convolutional Neural Network (CNN) for automated disaster identification.

### 2. Synthetic SMS Corpus

* **Source:** Synthetically generated to mimic real-world emergency communication.
* **Rationale:** Real distress signals are protected by telecommunication privacy laws.
* **Characteristics:** Includes typographical errors, slang, and panic-driven shorthand to simulate high-stress field conditions.
* **Labels:** Emergency, Urgent, Normal, Safe.

### 3. LLM-Augmented Resource Allocation Data

* **Source:** Generated using Large Language Models (LLMs) constrained by real-world NGO reporting heuristics.
* **Methodology:** We used baseline supply-chain data from NGO reports and expanded the feature space via LLM prompting to create diverse disaster scenarios.
* **Features:** Maps disaster severity (0-1) and urgency (tiers) to exact supply requirements (Water [L], Food [kg], Medical Kits, Tents).

## Getting Started

### Requirements

* Python 3.8+
* TensorFlow/Keras (for Image Data)
* Scikit-learn (for Text/Logistics Data)

### Data Preparation

For optimal results with the DRRO pipeline:

1. **Images:** Apply Z-score standardization.
2. **Text:** Use TF-IDF vectorization after removing stop-words.
3. **Logistics:** Apply Min-Max scaling to continuous supply variables.



## Data Availability Disclaimer

The SMS and Resource Allocation datasets are **synthetic/simulated**. They are intended for academic benchmarking and proof-of-concept testing. For deployment in life-critical systems, models should be fine-tuned on localized, field-validated data.

## Contact

Department of Computer Science and Business Systems

Nitte Meenakshi Institute of Technology (NMIT)

Bengaluru, India


