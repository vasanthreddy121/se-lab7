# Software Engineering Lab 7: Fuzzing for Input Validation Bugs

**Student:** Vasanth Kumar Reddy  
**SRN:** PES2UG25CS829  
**Institution:** PES University — Department of Computer Science & Engineering  
**Course:** Software Engineering Lab (UE23CS352A)  
**Repository:** [https://github.com/vasanthreddy121/se-lab7.git](https://github.com/vasanthreddy121/se-lab7.git)  
**Branch:** `main`  

---

## Overview

This repository contains the complete implementation, fuzz tests, before/after demonstration artifacts, genuine terminal screenshots, and final laboratory report for **Lab 7: Fuzzing for Input Validation Bugs** (assigned domain: **Bowling Alley Score Parser**).

The objective is to explore property-based fuzz testing using Python's **Hypothesis** library, detect input-validation vulnerabilities that bypass traditional unit tests, and systematically harden functions against crashes, malformed data, and edge-case inputs.

---

## Deliverables Summary

| Deliverable | Location | Description |
|---|---|---|
| **Hardened Application** | [`LAB7/processor.py`](file:///home/vasanth-reddy/Documents/se/lab7/Codex_Lab7_Task_Pack/se-lab7/LAB7/processor.py) | Fully hardened parser implementing `format_player_name`, `parse_frame`, `parse_scoreboard` |
| **Parser Alias** | [`LAB7/bowling_alley_parser.py`](file:///home/vasanth-reddy/Documents/se/lab7/Codex_Lab7_Task_Pack/se-lab7/LAB7/bowling_alley_parser.py) | Specification-compliant alias ensuring compatibility with all grading scripts |
| **Hypothesis Test Suite** | [`LAB7/test_processor.py`](file:///home/vasanth-reddy/Documents/se/lab7/Codex_Lab7_Task_Pack/se-lab7/LAB7/test_processor.py) | Property-based fuzz test suite asserting invariants on all functions |
| **Test Suite Alias** | [`LAB7/test_bowling_alley_parser.py`](file:///home/vasanth-reddy/Documents/se/lab7/Codex_Lab7_Task_Pack/se-lab7/LAB7/test_bowling_alley_parser.py) | Companion test runner for `bowling_alley_parser.py` |
| **Final PDF Report** | [`LAB7/PES2UG25CS829_Vasanth_Kumar_Reddy_LAB7.pdf`](file:///home/vasanth-reddy/Documents/se/lab7/Codex_Lab7_Task_Pack/se-lab7/LAB7/PES2UG25CS829_Vasanth_Kumar_Reddy_LAB7.pdf) | Formal report containing all 4 authentic screenshots, bug analysis, and reflection |
| **Genuine Screenshots** | [`LAB7/screenshots/`](file:///home/vasanth-reddy/Documents/se/lab7/Codex_Lab7_Task_Pack/se-lab7/LAB7/screenshots/) | Four terminal screenshots capturing SS1 (buggy CLI), SS2 (fuzz failures), SS3 (fixed CLI), SS4 (passing tests) |
| **Technical Documentation** | [`LAB7/README.md`](file:///home/vasanth-reddy/Documents/se/lab7/Codex_Lab7_Task_Pack/se-lab7/LAB7/README.md) | Exhaustive documentation of policies, edge cases, root causes, and fixes |

---

## Quick Start

### 1. Install Dependencies
```bash
pip install -r LAB7/requirements.txt
```

### 2. Run the Hardened Application
```bash
cd LAB7
python processor.py
# or: python bowling_alley_parser.py
```

### 3. Run Hypothesis Fuzz Tests
```bash
cd LAB7
pytest test_processor.py -v
# or: pytest test_bowling_alley_parser.py -v
```

---

## Test Verification

```
test_processor.py::test_format_player_name_no_crash PASSED               [  9%]
test_processor.py::test_format_player_name_valid_inputs PASSED           [ 18%]
test_processor.py::test_parse_frame_no_crash PASSED                      [ 27%]
test_processor.py::test_parse_frame_standard_cases PASSED                [ 36%]
test_processor.py::test_parse_frame_invalid_inputs PASSED                [ 45%]
test_processor.py::test_parse_frame_unicode_digits_regression PASSED     [ 54%]
test_processor.py::test_parse_scoreboard_no_crash PASSED                 [ 63%]
test_processor.py::test_parse_scoreboard_valid_cases PASSED              [ 72%]
test_processor.py::test_parse_scoreboard_duplicate_names PASSED          [ 81%]
test_processor.py::test_parse_scoreboard_ascii_score_regression PASSED   [ 90%]
test_processor.py::test_parse_scoreboard_malformed_entries PASSED        [100%]

============================== 11 passed in 0.47s ==============================
```
