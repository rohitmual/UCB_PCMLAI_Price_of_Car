# What Drives the Price of a Car?

## Project Overview

This project analyzes a dataset of 426,000 used car listings to identify the key factors that influence used car prices. The analysis follows the CRISP-DM (Cross-Industry Standard Process for Data Mining) framework and provides actionable recommendations for used car dealerships to optimize their inventory.

## Key Findings

At a uber level what a buyer really pays for is the change in a car's age and mileage; a newer car with low miles can fetch two to three times what an older, higher-mileage car sells for, and age plus odometer alone explain most of the price spread on the lot. After that, body type and drivetrain carry the rest of the weight: 4WD trucks, diesel pickups, and SUVs hold value far better than sedans or front-wheel-drive cars. For a dealership, the sweet spot is a 3–7-year-old, sub-60K-mile pickup or 4WD vehicle, these consistently sell for thousands more than average inventory.

The analysis identified the following primary drivers of used car prices:

| Factor | Impact on Price |
|--------|-----------------|
| **Vehicle Age** | Top driver (~45% of Random Forest feature importance). Median price drops from $32,590 at 0–3 yrs to $15,500 at 7–10 yrs (~52% loss). |
| **Odometer** | Second most important (~19%). <50K-mile vehicles command ~$11,800 over the 50–100K bucket (and ~$19,800 over 100K+). |
| **Drive Type** | 4WD trucks command +$14,250 over FWD equivalents; +$6,790 for pickups; +$905 for SUVs. |
| **Fuel Type** | Diesel trucks +$11,991 over gas; SUVs +$5,359; pickups +$2,860. |
| **Vehicle Type** | Pickups ($27,989 median) outperform sedans ($9,950 median). |

## Model Performance

| Model | R² Score | RMSE | MAE |
|-------|----------|------|-----|
| **Random Forest** | **0.833** | **$5,212** | **$2,947** |
| Gradient Boosting | 0.822 | $5,380 | $3,267 |
| Ridge Regression | 0.712 | $6,847 | $4,716 |

## Repository Structure

```
├── README.md              # This file
├── prompt_II.ipynb        # Main analysis notebook
├── data/
│   └── vehicles.csv       # Dataset (426K used car listings) [File .gitignore]
└── images/                # Supporting images
```

## Notebook

**[View the Analysis Notebook](prompt_II.ipynb)**

The notebook includes:
- Data exploration and visualization
- Data cleaning and preparation
- Multiple regression models with cross-validation and grid search
- Feature importance analysis
- Coefficient interpretation
- Business recommendations for dealerships

## Recommendations for Dealerships

1. **Target vehicles 3-7 years old** - best balance of price point and consumer demand
2. **Prioritize low-mileage vehicles** (<60K miles) - significant price premiums
3. **Stock 4WD trucks and pickups** - +$6,000-$14,000 premium over FWD
4. **Acquire diesel trucks and SUVs** - +$5,000-$12,000 premium over gas
5. **Focus on pickups, trucks, SUVs** over sedans for higher margins

## Requirements

- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## Usage

```bash
# Create virtual environment
python3 -m venv venv
source venv/bin/activate  # On fish: source venv/bin/activate.fish

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn

# Launch Jupyter
jupyter notebook prompt_II.ipynb
```
