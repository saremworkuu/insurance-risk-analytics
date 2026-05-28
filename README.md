# Insurance Risk Analytics

Project scaffold for exploratory analysis, hypothesis testing, and predictive modeling on insurance risk data.

## Structure

- `notebooks/` for analysis notebooks
- `src/` for reusable Python modules
- `data/` for DVC-managed datasets
- `reports/` for final deliverables
- `tests/` for automated checks

## Data Pipeline

This project uses DVC to version and manage large data files stored outside of Git. To reproduce the data locally, follow these steps:

1. Install DVC (if not already installed):

```
pip install dvc
```

2. Ensure your DVC remote is configured and you have the necessary credentials. You can list configured remotes with:

```
dvc remote list
```

3. Pull the tracked data files from the configured remote into the `data/` directory:

```
dvc pull
# or, to pull from a specific remote:
dvc pull -r <remote-name>
```

4. If this project contains a `dvc.yaml` pipeline, you can reproduce pipeline stages after pulling data with:

```
dvc repro
```

Notes:
- Data files are tracked under the `data/` directory and not stored in Git. `dvc pull` will populate `data/` with the required files.
- If you run into authentication issues, check your remote provider's credentials (AWS, GCP, Azure, or SSH) and consult DVC docs for provider-specific setup.
