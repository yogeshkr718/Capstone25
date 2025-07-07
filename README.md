# Capstone25
Absolutely bhai! Here’s a **complete and professional `README.md`** for your GitHub repo for:

🚗 **Real-Time Dynamic Parking Price Optimization using Pathway & Bokeh**

This includes:

* ✅ Project Overview
* 🧰 Tech Stack
* 🧱 Architecture Diagram (in Mermaid syntax)
* 🔄 Detailed Workflow
* 📁 Directory structure
* 📜 Optional extensions

---

````markdown
# 🚗 Real-Time Dynamic Parking Price Optimization

This project builds a smart, real-time parking price optimization system using live data streams, rule-based models, and interactive visualization. It adjusts parking lot prices dynamically based on occupancy, traffic, queue length, and even competition from nearby lots.

> ✅ Built using **Python**, **Pathway**, and **Bokeh**

---

## 📌 Project Features

- ⏱ Real-time data streaming using simulated CSV
- 📈 Dynamic pricing logic based on demand
- 🧠 Competitive pricing model (Model 3) compares nearby lots
- 📊 Interactive live dashboard using Bokeh
- 📂 Clean modular code and simulation-ready

---

## 🧰 Tech Stack

| Layer                 | Technology     | Description                                  |
|----------------------|----------------|----------------------------------------------|
| Language              | Python         | Core logic, models, simulation                |
| Data Handling         | Pandas         | Parsing, transformations                     |
| Streaming Engine      | Pathway        | Real-time processing of parking data         |
| Visualization         | Bokeh          | Real-time line chart of prices               |
| Input/Output Format   | CSV            | Simulated file-based stream and output       |
| IDE                   | Jupyter/Colab  | Interactive development                      |

---

## 🏗 Architecture Diagram

```mermaid
flowchart TD
    A[Parking Dataset (CSV)] --> B[streaming_input.csv]
    B --> C[Pathway Engine]
    C --> D[Pricing UDFs (Model 2 & 3)]
    D --> E[real_time_output.csv]
    E --> F[Bokeh Live Chart]
````

---

## 🧠 Pricing Models

### 🔹 Model 1: Linear

Simple model increasing price proportionally to occupancy.

### 🔹 Model 2: Demand-Based Pricing

Factors:

* Occupancy Ratio
* Queue Length
* Traffic Condition
* Special Day
* Vehicle Type Weight

**Formula**:

```
demand = α × occ_ratio + β × queue - γ × traffic + δ × special_day + ε × vehicle_weight
price = base_price × (1 + normalized_demand)
```

### 🔹 Model 3: Competitive Pricing

* Uses Haversine distance to find nearby lots within 500m
* Adjusts price based on:

  * Competitor prices
  * Own occupancy
  * Nearby availability

---

## ⚙️ Project Architecture and Workflow

### 🧱 Step-by-step:

1. **streaming\_input.csv** is created by copying `dataset.csv`
2. A simulation loop appends rows to `streaming_input.csv` every 2 seconds
3. **Pathway** reads streaming rows and applies `compute_price()` UDF
4. The UDF computes demand-based price and writes to `real_time_output.csv`
5. A **Bokeh app** reads this file and renders a live-updating price graph
6. Optionally, **rerouting logic** and **competition-aware pricing** are added via Model 3

---

## 📁 Directory Structure

```bash
project-root/
│
├── dataset.csv                  # Base dataset
├── streaming_input.csv          # Simulated real-time input
├── real_time_output.csv         # Output with dynamic prices
├── pathway_app.py               # Pricing logic with Pathway
├── bokeh_app.py                 # Live visualization
├── capstone_report.pdf          # Final report
├── README.md                    # This file
└── requirements.txt             # Python dependencies
```

---

## 🧪 How to Run Locally

1. Clone the repo:

```bash
git clone https://github.com/your-username/parking-price-optimizer.git
cd parking-price-optimizer
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run Pathway engine (in terminal or notebook):

```bash
python pathway_app.py
```

4. In another terminal, simulate row streaming:

```bash
python simulate_stream.py
```

5. Start Bokeh visualization:

```bash
bokeh serve bokeh_app.py --show
```

---

## 📈 Output Example

```csv
SystemCodeNumber,Occupancy,Price
LOT01,153,13.7
LOT02,108,11.4
...
```

---

## 🔮 Future Enhancements

* ML-based pricing (train regression on historical price behavior)
* Map-based UI with Folium or Leaflet
* User recommendation system based on route
* Surge pricing during events or peak hours
* Connect to real-time traffic API (like Google Maps)

---

## 📄 License

This project is for academic and educational use.
MIT License or as required by your institution.

---
```
