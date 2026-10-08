# Machine Learning Implementation Library

A clean, structured repository of foundational machine learning models. Each directory acts as a standalone environment containing the model training logic, evaluation metrics, and serialized model states for fast execution.

## Algorithm & Dataset Index

| Directory | Algorithm | Dataset | Task |
| :--- | :--- | :--- | :--- |
| `01_Linear_Regression/` | Linear Regression | California Housing | Continuous value prediction |
| `02_Logistic_Regression/` | Logistic Regression | Breast Cancer Wisconsin | Binary classification |
| `03_KNN/` | K-Nearest Neighbors | Iris | Multi-class distance grouping |
| `04_Decision_Tree/` | Decision Tree Classifier| Wine Quality | Rule-based classification |

## Architecture 

The repository is built to avoid redundant computations. Datasets are separated from the model logic, and trained models are cached.

*   **`data/`**: Centralized storage for raw and preprocessed `.csv` files.
*   **`utils/`**: Shared Python scripts for data cleaning and matplotlib configurations.
*   **`*.ipynb`**: Jupyter Notebooks containing the data pipeline and Scikit-Learn logic.
*   **`*.pkl`**: Serialized model weights (Joblib).

## Execution State (Bypassing Retraining)

Notebooks are designed with a conditional execution state. Upon running a notebook:

1. The script checks the local directory for a `model.pkl` file.
2. **Cache Hit:** If the file exists, it loads the model directly into memory, skipping the training pipeline entirely.
3. **Cache Miss:** If the file is missing, it executes the `.fit()` function on the dataset, trains the model, and dumps the state to disk for future runs.

## Local Setup

Ensure you have Python 3.10+ installed. 

```bash
# Clone the repository
git clone [https://github.com/yugp6488-commits/your-repo-name.git](https://github.com/yugp6488-commits/your-repo-name.git)
cd your-repo-name

# Install required dependencies
pip install pandas numpy scikit-learn matplotlib seaborn joblib
