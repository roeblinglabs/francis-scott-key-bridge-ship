# Francis Scott Key Bridge Vessel Collision Monitoring System

Real-time vessel collision monitoring system for the Francis Scott Key Bridge (Baltimore, Maryland).

## Overview

This system tracks vessels near the Francis Scott Key Bridge and assesses collision risk using:
- Real-time AIS (Automatic Identification System) vessel tracking
- Trajectory forecasting with linear projections
- AASHTO-based bridge impact force analysis
- Four-tier threat level system
- Grounding risk assessment

**Note:** The Francis Scott Key Bridge collapsed on March 26, 2024, after being struck by the container ship *Dali*. This monitoring system serves as a demonstration and memorial, showing how such incidents might be prevented at other high-risk bridges.

## Bridge Details

- **Location:** Baltimore, Maryland (39.217°N, 76.528°W)
- **Piers Monitored:** 10 piers (Piers 14-23)
- **Main Span:** Piers 17 & 18
- **Channel Depth:** ~50 feet
- **Status:** Demo system (bridge no longer exists)

## Running Locally

### Prerequisites
```bash
pip install -r requirements.txt
```

### Update Vessel Data
```bash
python3 update_ships.py
```

### Run Dashboard
```bash
streamlit run dashboard.py
```

The dashboard will open in your browser at `http://localhost:8501`

## Features

### Threat Levels

- 🔴 **ALARM** - Immediate collision risk requiring bridge closure
- 🟠 **ELEVATED MONITORING** - Large vessel approaching (routine transit)
- 🟡 **MONITOR** - Large vessel in area requiring routine tracking
- 🟢 **NEGLIGIBLE THREAT** - Safe passage expected

### Analysis Capabilities

- **Vessel Tracking:** Real-time positions from AIS transponders
- **Trajectory Prediction:** Linear projections at 5, 10, and 15-minute intervals
- **Impact Force Calculation:** AASHTO-based collision force estimates
- **Grounding Assessment:** Under-keel clearance analysis
- **Collision Probability:** Multi-factor risk assessment

## Technology Stack

- **Frontend:** Streamlit
- **Mapping:** Folium with custom markers
- **AIS Data:** AISStream.io API
- **Analysis:** Custom AASHTO-based algorithms
- **Deployment:** Streamlit Community Cloud

## Data Sources

- **Vessel Data:** AIS transponders via AISStream.io
- **Pier Locations:** Estimated from satellite imagery
- **Channel Depth:** ~50 feet (approximate)
- **Pier Capacity:** 5,000 kips (placeholder - requires structural analysis)

## NTSB Context

This system addresses NTSB Safety Recommendation 24-016, issued following the investigation of the Francis Scott Key Bridge collapse. The NTSB identified 68 high-risk bridges nationwide that require vessel detection and motorist warning systems.

## About Roebling Labs

**Roebling Labs LLC** develops vessel allision detection systems for bridges using AIS data and computer vision. Our mission is to prevent bridge-vessel collisions through early detection and real-time monitoring.

Contact: Vessel tracking, trajectory forecasting, and AASHTO bridge impact analysis

---

*In memory of the six construction workers who lost their lives in the Francis Scott Key Bridge collapse on March 26, 2024.*
