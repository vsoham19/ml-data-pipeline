📌 ML Data Pipeline

This project is a simple, modular data ingestion and validation pipeline designed to simulate how data is loaded and validated in industry-grade machine learning workflows before model training.

The goal of this project is to gain hands-on experience with pipeline structuring, separation of concerns, and data validation, which are critical in real-world ML systems.

📁 Project Structure
ml-data-pipeline/
│
├── data/
│   └── sample.csv
│
├── data_loader/
│   ├── __init__.py
│   ├── loader.py
│   └── validator.py
│
└── main.py

🧩 Component Overview
sample.csv

-Contains raw tabular data used as input for the pipeline.

data_loader/__init__.py

-Defines the public interface of the data_loader package by exposing the loader and validator functions.
-This enables clean and maintainable imports at the pipeline level.

loader.py

-Responsible for data ingestion.
-Checks whether the CSV file exists at the given path
-Loads the file into a pandas DataFrame
-Raises meaningful errors if the file is missing or empty
-This module focuses strictly on I/O handling, without applying any business or schema validation.

validator.py

-Responsible for data validation.
It enforces the following rules:
-Required columns must be present
-No missing or null values are allowed
-age and salary columns must contain numeric values
-If any validation fails, the pipeline raises an error and stops execution.

main.py

-Acts as the orchestration layer of the pipeline.
Execution flow:
-Accepts the input file path
-Loads the data using the loader module
-Validates the data using the validator module
-Confirms successful ingestion when all checks pass
-This structure mirrors how data pipelines are organized in production ML systems.

▶️ How to Run

From the project root:

python main.py

🚀 Key Learnings

-Modular pipeline design
-Separation of ingestion and validation logic
-Python package structuring using __init__.py
-Error handling in data workflows
-Foundations of real-world ML data pipelines
