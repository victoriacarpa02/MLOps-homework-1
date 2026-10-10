# MLOps Zoomcamp — Homework 1

A baseline model for predicting NYC yellow taxi trip duration.

Based on [Module 1 homework](https://github.com/DataTalksClub/mlops-zoomcamp/blob/main/cohorts/2025/01-intro/homework.md).

## Data and approach

- Training data: January 2023, Yellow Taxi Trip Records.
- Validation data: February 2023, Yellow Taxi Trip Records.
- Target: trip duration in minutes.
- Filter: keep durations between 1 and 60 minutes, inclusive.
- Features: pickup and drop-off location IDs, one-hot encoded with `DictVectorizer`.
- Model: `LinearRegression` with default parameters.
- Metric: root mean squared error (RMSE), measured in minutes.

The vectorizer and model are fitted on January data only.
February data is used for validation without retraining.

## Results

| Question | Computed result | Selected answer |
|---|---:|---:|
| Q1: Original column count | 19 | 19 |
| Q2: Duration standard deviation before filtering | 42.59 min | 42.59 |
| Q3: Records remaining after filtering | 98.12% | 98% |
| Q4: Encoded feature count | 515 | 515 |
| Q5: Training RMSE | 7.65 min | 7.64 |
| Q6: Validation RMSE | 7.81 min | 7.81 |

For Q5, the closest available answer is selected, as instructed in the homework.

## Run locally

Requirements: WSL/Linux and uv.

Run the following commands from the repository root.

Create a Python 3.12 environment if it does not already exist:

```bash
mkdir -p ~/.venvs
uv venv --python 3.12 ~/.venvs/mlops-homework-1
```

Activate the environment and install dependencies:

```bash
source ~/.venvs/mlops-homework-1/bin/activate
uv pip install -r requirements.txt
```

Start JupyterLab:

```bash
jupyter lab --no-browser
```

Open the URL printed in the terminal, select `homework.ipynb`,
and run all cells from top to bottom.

The notebook downloads the required Parquet files into `data/`.
Internet access is required for the initial download.
Downloaded datasets are excluded from Git.

## Validation

The notebook was successfully rerun using
**Restart Kernel and Run All Cells**.