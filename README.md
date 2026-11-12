# BTK-Drug-Discovery-Pipeline
Machine learning-based QSAR modeling and virtual screening of BTK inhibitors validated through molecular docking.
## Overview

Bruton's Tyrosine Kinase (BTK) is an important therapeutic target involved in B-cell receptor signaling and has emerged as a promising target for the treatment of B-cell malignancies and autoimmune disorders. This project combines **machine learning, molecular fingerprinting, virtual screening, and molecular docking** to identify potential novel BTK inhibitors from large chemical databases.

Machine learning models based on **Morgan fingerprints** were developed using known BTK inhibitor activity data, followed by virtual screening of a large natural-product compound library. Promising compounds were subsequently filtered using drug-likeness criteria and evaluated through molecular docking against BTK, using **Ibrutinib** as the reference inhibitor.

---

## Objectives

* Develop machine learning models for the identification of potential BTK inhibitors.
* Compare the performance of **Random Forest and XGBoost** models using Morgan molecular fingerprints.
* Virtually screen a large compound library to identify molecules with predicted BTK inhibitory activity.
* Apply drug-likeness filtering to prioritize promising candidates.
* Perform molecular docking of selected compounds against the BTK binding site.
* Compare the binding interactions of screened compounds with the reference inhibitor **Ibrutinib**.

---

## Dataset

The training dataset was compiled from:

* **ChEMBL**
* **BindingDB**

The combined dataset contained approximately **25,548 compounds** with experimentally reported activity information relevant to BTK.

Molecular structures were processed and represented using **Morgan fingerprints** for machine learning.

For virtual screening, **738,824 compounds** were obtained from the **COCONUT database**, providing a large natural-product chemical space for identifying potential novel BTK inhibitors.

---

## Methodology

The overall workflow consisted of the following stages:

```text
BTK Activity Dataset
        ↓
Data Collection & Preprocessing
        ↓
Molecular Structure Processing
        ↓
Morgan Fingerprint Generation
        ↓
Machine Learning Model Development
        ↓
Random Forest + XGBoost
        ↓
Model Evaluation
        ↓
Virtual Screening of COCONUT Database
        ↓
Predicted Active Compounds
        ↓
Drug-likeness Filtering
        ↓
Lead Candidate Selection
        ↓
Molecular Docking
        ↓
Interaction Analysis with BTK
        ↓
Comparison with Ibrutinib
```

### 1. Data Collection and Preprocessing

BTK bioactivity data were collected from ChEMBL and BindingDB. The dataset was processed to obtain suitable molecular structures and activity information for machine learning.

### 2. Molecular Fingerprint Generation

Molecular structures were converted into **Morgan fingerprints**, which encode structural features of the compounds in a machine-readable binary representation.

### 3. Machine Learning

Two supervised machine learning approaches were investigated:

* **Random Forest**
* **XGBoost**

The models were trained using Morgan fingerprints to classify compounds according to their predicted BTK inhibitory activity.

### 4. Model Evaluation

Model performance was assessed using multiple classification metrics, including:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC
* PR-AUC

### 5. Virtual Screening

The trained machine learning models were applied to **738,824 compounds from the COCONUT database** to identify compounds predicted to possess BTK inhibitory activity.

The virtual screening workflow identified **43,690 predicted active compounds**, which were subsequently subjected to additional filtering.

### 6. Drug-likeness Filtering

The predicted active compounds were further prioritized using:

* **Lipinski's Rule of Five**
* **Quantitative Estimate of Drug-likeness (QED)**

This filtering reduced the candidate pool to **32 final compounds** for molecular docking.

### 7. Molecular Docking

Selected compounds were docked against the BTK protein using **AutoDock Vina**.

**Ibrutinib** was used as the reference molecule to provide a benchmark for binding affinity and interaction analysis.

### 8. Binding Interaction Analysis

The docking poses were analyzed to evaluate:

* Binding affinity
* Protein–ligand interactions
* Hydrogen bonding
* Hydrophobic interactions
* Binding-site occupancy

The interactions of the screened compounds were compared with those observed for Ibrutinib.

---

## Machine Learning Results

### Random Forest

| Metric    |      Score |
| --------- | ---------: |
| Accuracy  | **0.7741** |
| Precision | **0.9424** |
| Recall    | **0.8004** |
| F1-score  | **0.8563** |
| ROC-AUC   | **0.7321** |
| PR-AUC    | **0.9602** |

The Random Forest model demonstrated good overall classification performance, with particularly high **precision and PR-AUC**, indicating effective identification of compounds predicted to belong to the active class.

### XGBoost

| Metric    |               Score |
| --------- | ------------------: |
| Accuracy  | **0.753142** |
| Precision | **0.947323** |
| Recall    | **0.771358** |
| F1-score  | **0.850332** |
| ROC-AUC   | **0.726794** |
| PR-AUC    | **0.959204** |

---

## Virtual Screening and Docking

The trained models were used to screen **738,824 compounds from COCONUT**, resulting in a set of predicted active compounds. Subsequent Lipinski and QED filtering was used to prioritize compounds with favorable drug-like properties.

The final **32 candidate compounds** were subjected to molecular docking against BTK and compared against Ibrutinib as the reference ligand.

The docking analysis focused on identifying compounds with favorable predicted binding affinities and interactions within the BTK active site.

---

## Tools & Technologies

### Programming & Data Analysis

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn

### Cheminformatics

* RDKit
* Morgan Molecular Fingerprints

### Machine Learning

* Random Forest
* XGBoost

### Molecular Docking & Visualization

* AutoDock Vina
* UCSF Chimera

### Databases

* ChEMBL
* BindingDB
* COCONUT

---

## Key Findings

* Machine learning models were successfully developed using molecular fingerprints to predict potential BTK inhibitors.
* The Random Forest model achieved an **accuracy of 77.41% and ROC-AUC of 0.7321**.
* The model showed particularly high **precision (94.24%) and PR-AUC (96.02%)**.
* Virtual screening was performed against **738,824 compounds** from the COCONUT database.
* Predicted active compounds were further prioritized using **Lipinski's Rule of Five and QED**.
* **32 compounds** were selected for molecular docking.
* Docking analysis was performed using **Ibrutinib as the reference inhibitor**.

---

## Conclusion

This study demonstrates an integrated **machine learning–virtual screening–molecular docking workflow** for the computational identification of potential BTK inhibitors. Combining Morgan fingerprint-based machine learning with large-scale virtual screening enabled the rapid prioritization of compounds from a large chemical library.

The subsequent drug-likeness filtering and molecular docking provided an additional level of prioritization for identifying promising candidates. The workflow can serve as a computational strategy for narrowing down large chemical libraries before experimental validation.

---

## Future Work

* Experimental validation of the top-ranked compounds.
* Further optimization of promising molecular scaffolds.
* Evaluation using additional molecular descriptors and fingerprint types.
* Ensemble or hybrid machine learning approaches.
* Molecular dynamics simulations to further investigate protein–ligand stability.

---

## Project Workflow

**Data Collection → Preprocessing → Morgan Fingerprints → Random Forest/XGBoost → Model Evaluation → COCONUT Virtual Screening → Lipinski/QED Filtering → Molecular Docking → Interaction Analysis**

---

