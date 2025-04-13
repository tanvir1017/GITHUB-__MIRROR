# 🔁 GitHub Repo Mirroring Guide

This project is a full mirror of the original private repository I contributed to at SM Technology. It includes all branches, full commit history, and tags. This guide explains how to mirror a GitHub repo — useful for backing up your contributions or archiving your work.

---

## ✅ Objective

Mirror a GitHub repository (including all branches, tags, and commit history) into a personal GitHub repo, without modifying the original.

---

## 📦 Prerequisites

- Access to the source (office/private) repository.
- Permission to use the mirrored content.
- A GitHub personal account with a new repository created (empty, no README).

---

## 🚀 Steps to Mirror a GitHub Repo

### 1. Clone the Source Repo as a Mirror

This will download the entire repository, including all branches and tags.

```bash
git clone --mirror <REPO_URL>
```

This creates a directory named `danange-server.git`, which is a **bare mirror** of the original repository — containing all branches, commit history, and tags, but no working directory (no files you can edit).

---

### 2. Create a New GitHub Repository

Go to https://github.com/new and create a new repository under your personal account.

- Name it appropriately (e.g., `chance-collective-server`)
- Keep it empty — do not initialize with a README, .gitignore, or license

---

### 3. Update the Remote Origin URL

Navigate into the mirrored repo and point it to your new personal repo.

```bash
cd danange-server.git
git remote set-url origin https://github.com/<your-username>/<your-repo>.git
```

For example:

```bash
git remote set-url origin <GITHUB PERSONAL REPO>
```

---

### 4. Push the Mirror to Your Personal Repo

Now push everything — all refs, branches, and tags — to your personal repo:

```bash
git push --mirror
```

This ensures that all commits, branches, and tags are now fully copied into your own repo.

---

### 5. Done! 🎉

Your personal GitHub repo now contains:

- All code
- All branches
- Full commit history
- All tags (if any)

---

## 🔄 How to Sync Changes Later

If your office repo continues development and you want to keep your personal mirror updated:

```bash
cd danange-server.git
git fetch origin --prune
git push --mirror
```

This will sync all new branches, commits, and deletions.

---

## 🧠 Notes

- This mirroring process is ideal for archiving or backing up a repository.
- You can’t `git checkout` branches inside the `.git` mirror directly.
- If you want a working copy of the repo, do a regular `git clone`.

---

## 🔒 Important Disclaimer

Make sure you have the legal and ethical right to mirror any private repository. This guide is intended for contributors and authorized users only. Do not mirror or republish code that you do not have permission to use.
