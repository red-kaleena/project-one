# GPA Calculator Web App

> CS3250 - Software Development Methods and Tools (Project 1)
> A simple web application that lets students track their GPA.

![Status](https://img.shields.io/badge/status-in_development-orange)
![CI](https://img.shields.io/badge/CI-not_configured-lightgrey)
![License](https://img.shields.io/badge/license-MIT-blue)

## Overview

Students register, log in, add the courses they completed together with their
letter grades, and instantly see their credit-weighted GPA. Every grade can be
updated or a course deleted. The app is a proof of concept built on a
Flask + SQLAlchemy baseline.

## Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| Framework | [Flask](https://flask.palletsprojects.com) | Web app |
| ORM | Flask-SQLAlchemy | Data access (`User`, `Course`, `Enrollment`) |
| Forms | Flask-WTF / WTForms | Signup, login, enrollment forms |
| Auth | Flask-Login | Session management |
| Hashing | bcrypt | Password hashing |
| Database | SQLite | Local `instance/prj1.db` |
| Activation | `gpa_calculator` | Credit-weighted GPA library (PyPI) |
| Testing | pytest | Unit tests for `gpa_calculator` |
| Linting | ruff | Code quality gate |
| Packaging | hatchling | Build for PyPI |
| Containers | Docker | Instructor-friendly deployment |

## Rubric Checklist

- [ ] **Planning: Schedule** — project timeline filled in (see [Schedule](#schedule))
- [ ] **Planning: Team Roles** — roles assigned (see [Team Roles](#team-roles))
- [ ] **Modeling: Use Case Diagram** — `uml/use_case.wsd`
- [ ] **Modeling: Class Diagram** — `uml/class.wsd`
- [ ] **Checkpoint** — diagrams + working baseline + protected main + schedule/roles
- [ ] **Courses data load** — ≥5 courses in `src/init_db.py`
- [ ] **Authentication** — signup, login, signout
- [ ] **List of Enrollments** — show all courses of the student
- [ ] **Create Enrollment** — add a course + grade
- [ ] **Delete Enrollment** — remove a course
- [ ] **GPA Calculation and Display** — credit-weighted, shown on enrollments page
- [ ] **GPA PyPI build and deployment** — `gpa_calculator` installable via pip
- [ ] **Testing** — manual test log (see [Testing Log](#manual-testing-log))
- [ ] **Deployment** — working `Dockerfile`
- [ ] **`main` branch protected** — no direct pushes

## Features

- [x] Baseline Flask + SQLAlchemy app
- [x] Data model: `User`, `Course`, `Enrollment`
- [x] Forms: signup, login, enrollment, delete
- [x] `dev` branch + protected `main`

### In progress / planned

- [ ] Implement signup / login / signout routes
- [ ] Seed ≥5 courses in `init_db.py`
- [ ] Implement `calculate_gpa` in `gpa_calculator`
- [ ] List / create / delete enrollments + GPA display
- [ ] Unit tests (`pytest`) + CI
- [ ] Publish `gpa_calculator` to PyPI
- [ ] Docker deployment

## Branch Model

```
feature/* ──PR──▶ dev ──PR──▶ main ──tag──▶ PyPI + Docker
```

- `main` — stable, protected, only via PR from `dev`.
- `dev` — integration branch for all feature work.
- `feature/*` — short-lived branches per task, created from `dev`.

## Getting Started

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

python src/init_db.py        # seed courses
cd src
flask --app app run          # http://127.0.0.1:5000
```

## gpa_calculator (published to PyPI)

`gpa_calculator` is our own library that computes the credit-weighted GPA. It is
packaged with hatchling (see `src/pyproject.toml`) and can be installed with:

```bash
pip install <package-name>
```

## Schedule

| Phase | Task | Start | End | Duration | Deliverable |
|---|---|---|---|---|---|
| Modeling | Requirements Analysis | mm/dd/26 | mm/dd/26 | .. days | Use Case Diagram |
| Modeling | Data Model | mm/dd/26 | mm/dd/26 | .. days | Class Diagram |
| Construction | Coding | mm/dd/26 | mm/dd/26 | .. days | Code |
| Construction | Testing | mm/dd/26 | mm/dd/26 | .. days | Test Report |
| Deployment | Delivery | mm/dd/26 | mm/dd/26 | .. days | Final Commit/Push |

## Team Roles

| Name | Role(s) |
|---|---|
| | manager, developer, tester, documenter |

## Manual Testing Log

| Functionality Tested | Date | Time | Result |
|---|---|---|---|
| Sign Up | mm/dd/26 | 00:00 | passed/failed |
| Login / Signout | mm/dd/26 | 00:00 | passed/failed |
| List Enrollments | mm/dd/26 | 00:00 | passed/failed |
| Create Enrollment | mm/dd/26 | 00:00 | passed/failed |
| Delete Enrollment | mm/dd/26 | 00:00 | passed/failed |
| Update Grade / GPA | mm/dd/26 | 00:00 | passed/failed |

## Team Evaluation

> Important: every member must submit the team/self-evaluation form —
> the team grade is held until all evaluations are in.