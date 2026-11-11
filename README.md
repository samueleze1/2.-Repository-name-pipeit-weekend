# PipeIt Weekend: My CI/CD Pipeline

[![CI/CD Pipeline](https://github.com/samueleze1/pipeit-weekend/actions/workflows/pipeline.yml/badge.svg)](https://github.com/samueleze1/pipeit-weekend/actions/workflows/pipeline.yml)

**Live Site:** https://samueleze1.github.io/pipeit-weekend/

## Project Overview

This project demonstrates my understanding of Continuous Integration and Continuous Deployment (CI/CD) using GitHub Actions.

I built this project during PipeIt Weekend by SKILL.SCH. The pipeline automatically runs tests, builds a status page using a custom GitHub Action, and deploys the generated website to GitHub Pages.

It also includes a scheduled workflow that runs automatically every day.

## CI/CD Pipeline Stages

1. **Trigger:** The pipeline runs when code is pushed to the `main` branch, on a scheduled basis, or manually.
2. **Test:** Runs automated checks using `bash tests/check.sh`.
3. **Build:** Uses my custom composite GitHub Action in `.github/actions/build-card` to generate the website.
4. **Deploy:** Publishes the generated website to GitHub Pages.

## Repository Structure

```text
pipeit-weekend/
├── .github/
│   ├── workflows/
│   │   ├── hello.yml
│   │   ├── ci.yml
│   │   └── pipeline.yml
│   └── actions/
│       └── build-card/
│           └── action.yml
├── tests/
│   └── check.sh
└── README.md
```

## Custom GitHub Action

I created a reusable composite GitHub Action that accepts two inputs:

- `name` – My name, used on the generated status page.
- `message` – An optional custom message.

The action generates `site/index.html` with information such as the workflow run number, commit details, timestamp, and GitHub Actions summary.

### Example Usage

```yaml
- name: Build status page
  uses: ./.github/actions/build-card
  with:
    name: Samuel Eze Anayo
    message: Built automatically by my own GitHub Action
```

## What I Learned

Through this project, I gained practical experience with:

- GitHub Actions workflows and triggers.
- Automating tests with CI pipelines.
- Using job dependencies with `needs:`.
- Creating reusable composite GitHub Actions.
- Passing inputs and generating outputs.
- Deploying websites with GitHub Pages.
- Reading workflow logs and debugging pipeline failures.

## Future Improvements

- [ ] Add more automated tests.
- [ ] Improve the generated status page.
- [ ] Add notifications for failed pipeline runs.
- [ ] Introduce additional deployment checks.

## About

**Created by Samuel Eze Anayo**

- GitHub: https://github.com/samueleze1
- Project: https://github.com/samueleze1/pipeit-weekend
- Live Site: https://samueleze1.github.io/pipeit-weekend/

Built as part of PipeIt Weekend by SKILL.SCH.
