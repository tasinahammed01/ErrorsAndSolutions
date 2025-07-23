## 📚 Table of Contents

- [List 1: Git Push Error](#Git Push Error: `non-fast-forward`)







## 🚧 Git Push Error: `non-fast-forward` – How to Resolve It

### ❓ Problem Description

When running:

```bash
git push
```
You may encounter this error:
```bash
! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'https://github.com/username/repo.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.

```


## ✅ Why This Happens
This happens when your local branch is behind the remote branch on GitHub. Someone else (or you from another machine) has already pushed new commits, and Git is blocking your push to avoid overwriting those changes.

## 🛠 How to Resolve It
You can fix this using one of the following methods:

🔁 Option 1: Pull and Merge (Safe & Recommended)

```bash
git pull origin main
// Resolve any merge conflicts if they appear //
git push origin main

```
This method merges the remote changes into your local branch safely.

🔄 Option 2: Rebase (Cleaner History)

```bash
git pull --rebase origin main
// Resolve conflicts if any //
git push origin main

```
This replays your changes on top of the updated remote branch.

⚠️ Option 3: Force Push (Dangerous)

```bash
git push --force

```

⚠️ Use only if you're absolutely sure. This overwrites the remote branch and can delete commits.

## 💡 Tip
To avoid this issue in the future, always pull the latest changes before pushing:
```bash
git pull origin main
```
