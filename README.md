# Recovery of OCT classifier predictions from decision-based attacks

Analysis notebook for a study of how six classical denoisers recover the predictions of an OCT retinal-image classifier (InceptionV3, run v2.1) after non-adaptive BO-DBA attacks built with five perturbation generators (Perlin, Gabor, BICU, BILI, CLUSTER).

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/thitimas/oct-denoising-study/blob/main/OCT_Generator_Study.ipynb)

## Contents

| Path | Description |
|---|---|
| `OCT_Generator_Study.ipynb` | Full analysis: data-integrity checks, baseline performance, attack characteristics, clean-image cost, recovery, pairwise tests, cohort consistency, class-level results, trade-offs, sensitivity analyses |
| `data/test_predictions_1.csv` | Classifier predictions on the 1,000-image test set (reference file) |
| `data/run_info_1.json` | Classifier training record |
| `data/New_All_Clean_OCT_2_.xlsx` | Six denoisers applied to the 1,000 clean test images |
| `data/*_PNG_<generator>.xlsx` | Attack results for each generator, cohort A (`240_…`) and cohort B (`More_240_…`) |
| `requirements.txt` | Python packages used by the notebook |

## Run in Google Colab

1. Click the **Open in Colab** badge above.
2. Choose **Runtime → Run all**. The first cell clones the repository and installs the packages; the last cell downloads the figures and tables as a zip.

For a private repository, add a GitHub personal access token as a Colab secret named `GITHUB_TOKEN` (key icon in the left sidebar) before running.

## Run locally

```bash
git clone https://github.com/thitimas/oct-denoising-study.git
cd oct-denoising-study
pip install -r requirements.txt
jupyter notebook OCT_Generator_Study.ipynb
```

Outputs (PDF and PNG figures, CSV and LaTeX tables, and a manifest) are written to `outputs/`.

## Data

Images come from the public Kermany OCT dataset (v3). The spreadsheets contain model predictions and attack measurements, not images.
