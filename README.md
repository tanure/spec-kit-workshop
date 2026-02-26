<div align="center">

<br>

```
███████╗██████╗ ███████╗ ██████╗    ██╗  ██╗██╗████████╗
██╔════╝██╔══██╗██╔════╝██╔════╝    ██║ ██╔╝██║╚══██╔══╝
███████╗██████╔╝█████╗  ██║         █████╔╝ ██║   ██║   
╚════██║██╔═══╝ ██╔══╝  ██║         ██╔═██╗ ██║   ██║   
███████║██║     ███████╗╚██████╗    ██║  ██╗██║   ██║   
╚══════╝╚═╝     ╚══════╝ ╚═════╝    ╚═╝  ╚═╝╚═╝   ╚═╝   
```

# Spec-Driven Development with GitHub Spec Kit

### The Complete Beginner's Guide to Building Better Software with AI-Powered Specifications

[![Live eBook](https://img.shields.io/badge/📖_Live_eBook-Read_Now-3B82F6?style=for-the-badge)](https://tanure.github.io/spec-kit-ebook/)
[![GitHub Pages](https://img.shields.io/badge/Hosted_on-GitHub_Pages-222?style=for-the-badge&logo=github)](https://pages.github.com/)
[![Spec Kit](https://img.shields.io/badge/GitHub_Spec_Kit-68k+_⭐-FBBF24?style=for-the-badge&logo=github)](https://github.com/github/spec-kit)

<br>

<img src="https://img.shields.io/badge/VS_Code-007ACC?style=flat-square&logo=visual-studio-code&logoColor=white" alt="VS Code">
<img src="https://img.shields.io/badge/GitHub_Copilot-000?style=flat-square&logo=github-copilot&logoColor=white" alt="Copilot">
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
<img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React">

</div>

---

## 🧭 What is This?

A **free, open-knowledge ebook** that teaches you how to stop vibe coding and start building software with structured AI specifications using [GitHub Spec Kit](https://github.com/github/spec-kit).

Whether you're a beginner or experienced developer, this guide walks you through the entire Spec-Driven Development workflow — from setting up your environment to building a complete **HabitTracker** app, all with copy-paste-ready prompts.

> *"Doing exactly what I asked and NOTHING more is a glowing endorsement. That is how agentic coding becomes viable at the enterprise level."*
> — GitHub Spec Kit Community

## 📚 What's Inside

| Chapter | Topic | What You'll Learn |
|---------|-------|-------------------|
| **01** | The Problem with Vibe Coding | Why unstructured AI coding fails at scale |
| **02** | What is Spec-Driven Development? | The four pillars and philosophy of SDD |
| **03** | Introducing GitHub Spec Kit | The 7 slash commands and project structure |
| **04** | Setting Up Your Environment | From zero to working project in 10 minutes |
| **05** | The SDD Workflow Deep Dive | Each phase with examples and best practices |
| **06** | Token Optimization | How SDD reduces AI token consumption by ~60% |
| **07** | Project: Build a HabitTracker | Complete hands-on build with every prompt |

Plus an **Appendix** with slash commands quick reference and an **About the Authors** section.

## 🚀 Read the eBook

The ebook is hosted as a single-page web application on GitHub Pages:

**👉 [https://YOUR_USERNAME.github.io/spec-kit-ebook/](https://YOUR_USERNAME.github.io/spec-kit-ebook/)**

Features of the web version:
- Dark editorial design with scroll animations
- Mobile-responsive layout
- Copy-paste-ready code blocks and prompts
- Interactive table of contents
- No dependencies — pure HTML/CSS/JS

## 🏗️ Repository Structure

```
spec-kit-ebook/
├── main                          ← You are here
│   ├── README.md                 # This file
│   └── .github/
│       └── workflows/
│           └── deploy.yml        # GitHub Actions: deploys gh-pages branch
│
└── gh-pages                      ← Deployed to GitHub Pages
    └── index.html                # The ebook (single-file web app)
```

The `main` branch contains the source of truth (README, CI/CD config). The `gh-pages` branch contains the deployable `index.html` that GitHub Pages serves. The GitHub Actions workflow automates deployment whenever the `gh-pages` branch is updated.

## ⚙️ Setup Guide

### 1. Create the repo and push `main`

```bash
# Clone your new repo
git clone https://github.com/YOUR_USERNAME/spec-kit-ebook.git
cd spec-kit-ebook

# Copy in the README, workflow, etc.
# (these files are already in this repo)

git add .
git commit -m "Initial setup: README + GitHub Actions"
git push origin main
```

### 2. Create the `gh-pages` branch with the ebook

```bash
# Create an orphan branch (clean history for Pages)
git checkout --orphan gh-pages

# Remove all files from the working tree
git rm -rf .

# Copy your ebook HTML as index.html
cp /path/to/Spec-Driven-Development-with-GitHub-Spec-Kit.html index.html

git add index.html
git commit -m "Deploy ebook v1.0"
git push origin gh-pages

# Switch back to main
git checkout main
```

### 3. Enable GitHub Pages

1. Go to **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: **`gh-pages`** / `/ (root)`
4. Click **Save**

Your ebook will be live within a minute at `https://YOUR_USERNAME.github.io/spec-kit-ebook/`.

### 4. GitHub Actions (automatic deployment)

The workflow at `.github/workflows/deploy.yml` runs automatically when:
- You push changes to the `gh-pages` branch
- You manually trigger it from the Actions tab (workflow_dispatch)

This gives you a clean CI/CD pipeline so that any AI agent (GitHub Copilot, Claude, etc.) can update the ebook content on the `gh-pages` branch and the deployment happens automatically.

## 🤖 Updating the eBook with AI Agents

The whole point of hosting on `gh-pages` with GitHub Actions is to enable **agent-driven content updates**. Here's the workflow:

```
1. AI agent checks out the gh-pages branch
2. Edits index.html (add chapter, fix content, update styling)
3. Commits and pushes to gh-pages
4. GitHub Actions automatically deploys the update
5. Live site reflects changes within ~60 seconds
```

You can trigger this from:
- **GitHub Copilot** in VS Code — edit the HTML directly
- **Claude Code** — `git checkout gh-pages && edit index.html && git push`
- **Any GitHub-connected agent** — via the GitHub API or Git CLI
- **Manual workflow dispatch** — from the Actions tab in GitHub

## 🛠️ GitHub Actions Workflow

The deploy workflow (`.github/workflows/deploy.yml`) does the following:

```yaml
# Triggers on push to gh-pages or manual dispatch
# → Checks out gh-pages branch
# → Deploys to GitHub Pages using actions/deploy-pages
```

This is intentionally lightweight — the `gh-pages` branch IS the deployment artifact. The workflow simply tells GitHub Pages to pick up the latest version.

## 📖 Available Formats

| Format | Description | Location |
|--------|-------------|----------|
| **HTML** (web) | Interactive single-page ebook | `gh-pages` branch → GitHub Pages |
| **PDF** (premium) | Dark-themed, print-ready ebook | Available as a release artifact |
| **DOCX** (editable) | Word document for editing | Available as a release artifact |

## 👥 Authors

**Albert Tanure** — Cross Solutions Architect at Microsoft · Docker Captain · Former Microsoft MVP (7 years)
[LinkedIn](https://www.linkedin.com/in/albert-tanure/) · [GitHub](https://github.com/tanure) · [Tanure.io](https://tanure.io)

**Rodrigo Moreirao** — Cloud Solution Architect at Microsoft · DevSecOps & GitHub Specialist
[LinkedIn](https://www.linkedin.com/in/rodrigo-moreirao-059a8120/)

## 📄 License

This ebook is **open knowledge** — share freely, learn openly, build better software.

---

<div align="center">

**Stop vibe coding. Start building with intent.**

[![Spec Kit](https://img.shields.io/badge/Powered_by-GitHub_Spec_Kit-3B82F6?style=for-the-badge&logo=github)](https://github.com/github/spec-kit)

</div>
