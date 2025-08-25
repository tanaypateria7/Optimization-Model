# Optimization-Model
Car Sales Optimization using Linear Programming. This project demonstrates how to use Linear Programming (LP) with Python's PULP library to optimize car sales decisions for maximum profit under budget and inventory constraints.
Car Sales Optimization Model
Overview
This project uses Linear Programming (LP) with Python's PuLP library to solve a real-world
business problem:
How can we maximize profit by deciding how many cars of each model to sell under budget and
inventory constraints?
The model demonstrates three key components:
1. Setup ® Problem formulation with objective & constraints
2. Solution ® Optimization using PuLP Solver
3. Insights ® Business interpretation with visualizations
Dataset
- The dataset contains details about Car Models, Prices, Profit per Unit, and Available Units.
- Example columns:
- Model
- Price
- ProfitPerUnit
- AvailableUnits
1. Problem Setup
Decision Variables
- x_i: Number of units of car model i to sell
Objective Function
Maximize total profit:
Maximize Z = S (Profit_i × x_i)
Constraints
1. Budget Constraint:
S (Price_i × x_i) £ Budget
2. Inventory Constraint:
x_i £ AvailableUnits_i
3. Capacity Constraint (optional):
S x_i £ MaxCars
2. Solution
- Implemented using PuLP with the CBC solver.
- Solver finds the optimal number of cars to sell for maximum profit while satisfying constraints.
- Supports time limits for faster solving on large datasets.
Example run:
model.solve(pulp.PULP_CBC_CMD(msg=0, timeLimit=30))
3. Insights
- Optimal Plan: Car models and units to sell for maximum profit.
- Profit Analysis: Which models contribute most to profit.
- Scenario Analysis: Changing budget or constraints affects decisions.
- Visualizations:
- Bar chart of optimal units
- Boxplots for price/profit distributions
Requirements
Install dependencies:
pip install pulp pandas matplotlib seaborn
How to Run
1. Place the dataset 'Car Sales.csv' in the project folder.
2. Run the Python script:
python car_sales_optimization.py
3. View the output in the console and visualizations in plots.
Future Improvements
- Add multiple objectives (e.g., profit + customer demand).
- Support multiple constraints like manpower, storage, etc.
- Interactive dashboards with Plotly or Power BI.
