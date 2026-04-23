# Drought Relief Pipeline

A scalable data pipeline for processing drought-relief claims, combining batch processing with real-time validation.

---

## Overview

This project simulates a government relief system where claims are processed in two stages:

- **Batch Processing:** Prepare payout tables using pandas  
- **Live Validation:** Validate incoming claims in real time using efficient data structures  

The goal is to demonstrate how choosing the right tools (vectorized operations vs lookup-based structures) affects performance, scalability, and reliability.

---

## Key Features

- Batch payout processing using pandas  
- Real-time validation using dictionary and set lookups  
- Duplicate detection and eligibility filtering  
- District-level rule enforcement  
- Performance benchmarking (slow vs optimized approaches)  
- Safe aggregation with failure handling  

---

## Architecture

| Component            | Tool Used       | Reason |
|---------------------|---------------|--------|
| Batch Processing     | pandas         | Efficient vectorized operations on large datasets |
| Live Validation      | dict / set     | Constant-time (O(1)) lookups for streaming data |
| Benchmarking         | Python timing  | Compare performance across approaches |
| Aggregation          | Custom logic   | Robust handling of missing and duplicate data |

---

## Performance Insight

The optimized live validator significantly outperforms the naive row-by-row approach by:
- Avoiding repeated DataFrame scans  
- Using precomputed lookup structures  
- Reducing complexity from linear scans to constant-time checks  

---

## Project Structure
### Main implementation 
drought_relief_pipeline.ipynb 
### Project documentation
README.md 


---

## Key Learnings

- Batch and real-time systems require different abstractions  
- pandas is powerful for bulk processing but inefficient for per-row streaming  
- Lookup-based data structures (dict/set) are critical for real-time systems  
- Clean separation between batch and live layers improves scalability and clarity  

---

## How to Run

1. Open the notebook in Google Colab or Jupyter Notebook  
2. Run all cells sequentially  
3. Review outputs and benchmark comparisons  

---

## Author

Riya Dewan  
Ashoka University
