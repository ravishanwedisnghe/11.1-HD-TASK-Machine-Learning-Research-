# SIT307 — 11.1 HD Task: Machine Learning Research

## Overview
This project reproduces the methods in “An efficient stacking-based ensemble technique for early heart attack prediction” and tests a modified stacking approach.

Part 1 reproduces six individual models and their stacking ensemble.
Part 2 removes exact duplicates and compares stacking variants using repeated stratified cross-validation.

## Files
- `11_1_HD_TASK_(Machine_Learning_Research).ipynb`: code, explanations, experimental outputs, and comparisons.
- `heart_3.csv`: dataset used for the experiments.
- `11.1 HD TASK (Machine Learning Research).pdf`: technical report.
- `README.md`: setup and running instructions.

## Requirements
The project uses Python and these packages:
- pandas
- numpy
- scikit-learn
- xgboost
- scipy
- matplotlib
- seaborn

## Run in Google Colab
1. Download the notebook and `heart_3.csv` from this repository.
2. Open Google Colab and upload the notebook.
3. Upload `heart_3.csv` using the Files panel.
4. Keep the dataset filename exactly as `heart_3.csv`.
5. Install the required packages if needed:

```python
%pip install pandas numpy scikit-learn xgboost scipy matplotlib seaborn
```

6. Select Runtime → Run all.
7. Wait for all experiments to finish. Part 2 includes repeated validation and parameter searches, so it takes longer.
8. Review the results tables, statistical comparisons, and plots.

No separate build step is required.

## Reproducing the Results
Run all cells in order in a fresh session. Keep the dataset, random seeds, model settings, and validation settings unchanged.

Part 1 uses a stratified 80/20 split.
Part 2 uses five-fold stratified cross-validation repeated five times, giving 25 outer test folds.

The notebook reports Accuracy, Precision, Recall, F1 Score, and AUC. Small numerical differences may occur with different software versions.

## Findings and Limitations
Part 1 contains exact duplicate overlap between training and testing. Its perfect stacking scores therefore need caution.

Part 2 evaluates unique records. The full proposed method increases average recall compared with the clean baseline stack, but reduces precision and specificity. Corrected statistical tests do not establish a clear improvement.

The internal tuning and threshold procedure is not fully nested. The dataset has no patient identifiers, so unique records cannot be confirmed as unique patients. This project is an academic experiment, not a validated medical tool.

## Selected Paper
M. Bhagat, A. Sharma, and P. Agarwal, “An efficient stacking-based ensemble technique for early heart attack prediction,” Multimedia Tools and Applications, vol. 84, pp. 36351–36375, 2025.
DOI: https://doi.org/10.1007/s11042-024-19293-7
