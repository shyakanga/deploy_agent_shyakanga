# Project: Automated Project Bootstrapping & Process Management

At the root of the project is a shell script (`setup_project.sh`) that bootstraps environment setup for the **Student Attendance Tracker**.

---

## Usage

Run the setup script:

```bash
bash setup_project.sh
```

Then follow the prompts:

1. Enter a string for your project directory, this creates `attendance_tracker_{input}/`
2. Optionally update **Warning** or **Failure** thresholds in `config.json`

---

## Features

### Environment Validation
Automatically checks if `python3` is installed before running the script.

### Dynamic Configuration
`sed` is used to update thresholds in `config.json` based on your input.

### Process Management (Signal Trap)
If `SIGINT` (`Ctrl+C`) is triggered during execution, the script will automatically archive the current state of the directory into `attendance_tracker_{input}_archive.tar.gz` and Delete the incomplete directory.

---

## Note

Ensure the script has execution permissions, run this to ensure it has that permission:

```bash
chmod +x setup_project.sh
```
