# Hyderabad Road Risk AI 🚦
### AI-Powered Road Risk Prediction and Accident Analysis System

## 📌 Overview

Hyderabad Road Risk AI is an intelligent road safety analysis system that uses Machine Learning to identify and classify potentially risky road segments across Hyderabad.

The project combines OpenStreetMap road network data, historical accident information, weather conditions, road geometry features, and a LightGBM classification model to predict road risk levels.

The system provides an interactive map-based dashboard where users can explore road segments, search for roads, view risk classifications, and examine historical accident information.

## 🎯 Objectives

- Identify potentially high-risk road segments across Hyderabad.
- Predict road risk levels using Machine Learning.
- Visualize road safety information through an interactive map.
- Analyze historical accident patterns.
- Provide road-level risk information to support safer transportation planning.

## ✨ Key Features

### 1. Interactive Road Risk Map
- Visualize Hyderabad's road network.
- Display road risk classifications using map-based visualization.
- Explore road segments interactively.

### 2. Machine Learning Risk Prediction
- Uses a trained LightGBM classification model.
- Classifies roads into three risk categories:
  - 🟢 Low Risk
  - 🟡 Medium Risk
  - 🔴 High Risk
- Displays prediction confidence and class probabilities.

### 3. Road Search
- Search roads by name.
- View road type, estimated speed, lanes, and road length.
- Display the highest predicted risk among matching road segments.
- View aggregated historical accident counts.

### 4. Accident Analysis
- Displays historical accident information.
- Includes accident location, date, weather, cause, severity, casualties, and traffic density.
- Supports geographical accident visualization.

### 5. Dashboard Statistics
- Total number of road segments.
- Low-, medium-, and high-risk road counts.
- Average prediction confidence.

## 🧠 Machine Learning Model

The project uses **LightGBM (Light Gradient Boosting Machine)** for multi-class road risk classification.

### Input Features

The model uses road-related features such as:

- Highway type
- Maximum speed
- One-way information
- Road length
- Number of lanes
- Geometry points
- Endpoint distance
- Geometry complexity
- Straightness

### Risk Classification

| Class | Risk Level |
|---|---|
| 0 | Low |
| 1 | Medium |
| 2 | High |

The model generates a predicted risk category along with prediction probabilities.

## 🛠️ Technology Stack

| Component | Technology |
|---|---|
| Programming Language | Python |
| Machine Learning | LightGBM |
| Data Processing | Pandas |
| Model Serialization | Joblib |
| Backend | Flask |
| Frontend | HTML, CSS, JavaScript |
| Mapping | Leaflet.js |
| Road Network Data | OpenStreetMap / OSMnx |
| Weather Data | Open-Meteo |
| Development Environment | VS Code |

## 📂 Project Structure

```text
hyderabad-road-risk-ai/
│
├── app/
│   ├── app.py
│   └── index.html
│
├── models/
│   └── road_risk_model.pkl
│
├── data/
│   ├── hyderabad_accidents_clean.csv
│   └── hyderabad_ml_predictions.csv
│
├── scripts/
│
├── requirements.txt
├── .gitignore
└── README.md
```

**Note:** The large prediction dataset is excluded from the GitHub repository. The required datasets must be placed inside the `data/` directory locally before running the application.

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/sahasrayeruva/-Road-Segment-Risk-Classification-Using-Decision-Trees-and-LightGBM
.git
```

### 2. Navigate to the Project

```bash
cd hyderabad-road-risk-ai
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

### 4. Activate the Environment

Windows:

```bash
venv\Scripts\activate
```

### 5. Install Dependencies

```bash
pip install -r requirements.txt
```

### 6. Add Required Data Files

Place the following files in the `data/` directory:

```text
hyderabad_accidents_clean.csv
hyderabad_ml_predictions.csv
```

The trained model should be available at:

```text
models/road_risk_model.pkl
```

### 7. Run the Application

```bash
cd app
python app.py
```

### 8. Open in Browser

```text
http://127.0.0.1:5000
```

## 🔌 API Endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/` | GET | Main dashboard |
| `/api/stats` | GET | Dashboard statistics |
| `/api/search?q=roadname` | GET | Search roads |
| `/api/roads` | GET | Retrieve medium- and high-risk roads |
| `/api/predict` | POST | Predict road risk using LightGBM |
| `/api/accidents` | GET | Retrieve historical accident records |

### Example Prediction Request

`POST /api/predict`

```json
{
  "highway": "primary",
  "maxspeed": 50,
  "oneway": 1,
  "reversed": 0,
  "length": 250,
  "lanes": 2,
  "geometry_points": 10,
  "endpoint_distance": 200,
  "geometry_complexity": 1.2,
  "straightness": 0.85
}
```

The API returns a predicted risk category, confidence, and class probabilities.

## 📊 Data Sources

- **OpenStreetMap:** Road network and road attributes.
- **Open-Meteo:** Weather information.
- **Kaggle:** Indian Road Accident Dataset (2022–2025).

Some accident-related contextual attributes were synthetically generated during dataset preparation. Therefore, predictions should be interpreted as experimental model outputs rather than verified official road safety assessments.

## 🚀 Future Enhancements

- Real-time traffic data integration.
- Live accident reporting.
- Improved model accuracy and validation.
- Route-based risk assessment.
- Accident hotspot detection.
- Mobile application integration.
- City-wide expansion beyond Hyderabad.

## ⚠️ Disclaimer

This project is developed for educational, research, and experimental purposes. Predictions are not official safety ratings and should not be used as the sole basis for driving or transportation decisions.

## 👨‍💻 Author

**Sahasra Yeruva
  Mahathi Chekka**

B.Tech – Computer Science & Information Technology

GitHub: [sahasrayeruva](https://github.com/sahasrayeruva)

---

⭐ If you find this project interesting, consider giving the repository a star!
