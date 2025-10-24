# Git Push Guide - Git Bash Commands

This guide provides the essential Git commands for pushing code to the repository using Git Bash.

## Prerequisites

Before pushing code, ensure you have:
- Git installed on your system
- Git Bash configured
- Repository cloned to your local machine
- Proper access rights to the repository

## Basic Push Workflow

### 1. Check Current Status
```bash
git status
```
This shows which files have been modified, added, or deleted.

### 2. Stage Your Changes
```bash
# Stage all changes
git add .

# Stage specific file
git add filename.ext

# Stage multiple files
git add file1.txt file2.js file3.css
```

### 3. Commit Your Changes
```bash
# Commit with a message
git commit -m "Your descriptive commit message"

# Commit with a detailed message (opens editor)
git commit
```

### 4. Push to Remote Repository
```bash
# Push to the current branch
git push

# Push to specific branch
git push origin branch-name

# Push to main/master branch
git push origin main

# Force push (use with caution!)
git push -f origin branch-name
```

## Complete Push Command Sequence

Here's the typical sequence for pushing code:

```bash
# 1. Check what has changed
git status

# 2. Stage all changes
git add .

# 3. Commit with a message
git commit -m "Add new feature or fix bug"

# 4. Push to remote repository
git push origin main
```

## Common Scenarios

### First Time Push (New Repository)
```bash
git remote add origin https://github.com/solid-arafat/portfolio-web.git
git branch -M main
git push -u origin main
```

### Push to a New Branch
```bash
# Create and switch to new branch
git checkout -b feature-branch

# Make your changes, then:
git add .
git commit -m "Feature description"
git push -u origin feature-branch
```

### Push After Pulling Latest Changes
```bash
# Pull latest changes first
git pull origin main

# Resolve any conflicts if they occur

# Then push your changes
git add .
git commit -m "Your changes"
git push origin main
```

## Useful Commands

### Check Remote Configuration
```bash
git remote -v
```

### View Commit History
```bash
git log
git log --oneline
git log --graph --oneline --all
```

### View Differences
```bash
# Show unstaged changes
git diff

# Show staged changes
git diff --staged

# Show changes in specific file
git diff filename.ext
```

### Undo Changes (Before Pushing)
```bash
# Unstage a file
git reset HEAD filename.ext

# Discard changes in working directory
git checkout -- filename.ext

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1
```

## Troubleshooting

### Push Rejected
If your push is rejected, it usually means the remote has changes you don't have locally:
```bash
# Pull and merge first
git pull origin main

# Or pull with rebase
git pull --rebase origin main

# Then push
git push origin main
```

### Authentication Issues
```bash
# If using HTTPS, you may need to set up credentials
git config --global credential.helper store

# For SSH, ensure your SSH key is added
ssh-add ~/.ssh/id_rsa
```

### Set Default Push Behavior
```bash
# Push only current branch
git config --global push.default current

# Push all matching branches
git config --global push.default matching
```

## Best Practices

1. **Always pull before push**: `git pull origin main` before pushing
2. **Write clear commit messages**: Describe what and why, not how
3. **Commit frequently**: Small, logical commits are easier to manage
4. **Review before committing**: Use `git status` and `git diff`
5. **Use branches**: Keep main/master stable, work on feature branches
6. **Test before pushing**: Ensure your code works before pushing

## Quick Reference

| Command | Description |
|---------|-------------|
| `git status` | Check status of files |
| `git add .` | Stage all changes |
| `git add <file>` | Stage specific file |
| `git commit -m "message"` | Commit with message |
| `git push` | Push to current branch |
| `git push origin <branch>` | Push to specific branch |
| `git pull` | Pull latest changes |
| `git log` | View commit history |
| `git diff` | View changes |
| `git branch` | List branches |
| `git checkout <branch>` | Switch branch |

## Repository Information

- **Repository**: solid-arafat/portfolio-web
- **Remote URL**: https://github.com/solid-arafat/portfolio-web

## Example: Complete Workflow

```bash
# Clone repository (first time only)
git clone https://github.com/solid-arafat/portfolio-web.git
cd portfolio-web

# Make your changes to files...

# Check what changed
git status

# Stage all changes
git add .

# Commit changes
git commit -m "Update portfolio content"

# Push to remote
git push origin main
```

---

**Note**: Replace `main` with your default branch name if different (could be `master` or another branch name).
