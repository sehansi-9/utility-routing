

## Table of Contents

- [Pre-OCR Utility Routing for Lightweight Document Image Classification](#pre-ocr-utility-routing-for-lightweight-document-image-classification)
  - [Repository files](#repository-files)
  - [Reproduce the utility-router results](#reproduce-the-utility-router-results)
  - [Environment](#environment)

# Pre-OCR Utility Routing for Lightweight Document Image Classification

This project investigates when a lightweight document classifier should use optical character recognition (OCR). A quality-based rule selects between an image-only prediction and image–text fusion. A separate exploratory router predicts the benefit of fusion from information available before OCR.

## Repository files

- `original tests and checkpoints.ipynb`: the original experiment and analysis notebook.
- `reproducing router results.ipynb`: the notebook containing the locked-fold utility-router reproduction cell.
- `README.md`: this guide.

The saved experiment inputs and results are archived in `ocr_invoke.zip` on Zenodo. The archive and notebooks are available under DOI **10.5281/zenodo.24443816**.
https://zenodo.org/records/24443816
## Reproduce the utility-router results

The reproduction cell refits four random-forest utility models using cached image and fusion predictions and the original saved source folds. It checks the four evaluation panels at 40% OCR use.

1.  Download `ocr_invoke.zip` from the Zenodo record.
2.  Create a Kaggle dataset from the archive contents and attach it to a new Kaggle notebook. The attached input must contain `all_predictions.csv` and `out_of_fold_scores.csv`, each exactly once.
3.  Open `reproducing router results.ipynb` and run the cell titled `REBUILD UTILITY ROUTERS USING ORIGINAL SOURCE FOLDS`.
4.  Compare the printed results with the table below. Outputs are saved under `/kaggle/working/reproducibility_release_v1/`.

## Environment

The router reproduction check was run with Python 3.13.18, NumPy 2.1.3, pandas 2.3.3, SciPy 1.16.3 and scikit-learn 1.6.1. It does not require rerunning OCR or the CNN.

The original experiment additionally uses PyTorch, torchvision, OpenCV, Pillow, pytesseract and Tesseract. The saved run configuration records the original experiment versions and settings.


The reproduction check validates selected utility-router results from saved predictions. It does **not** independently reproduce CNN training, OCR, all tables, or live deployment latency.
