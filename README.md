<a name="TOP"></a>

![Git Cheatsheet](https://placehold.co/1000x100/transparent/999?text=Git%20Cheatsheet&font=source-sans-pro)

## 📌 The Core Workflow (The Daily Loop)

This is the standard lifecycle of an update. Run through these steps multiple times a day as you build features or fix bugs.

```mermaid
graph LR
    A[Working Directory] -- git add --> B[Staging Area]
    B -- git commit --> C[Local Repository]
    C -- git push --> D[Remote GitHub]
    style A fill:#f9f9f9,stroke:#333,stroke-width:1px
    style B fill:#e1f5fe,stroke:#03a9f4,stroke-width:2px
    style C fill:#e8f5e9,stroke:#4caf50,stroke-width:2px
    style D fill:#eceff1,stroke:#607d8b,stroke-width:2px
```

## Check what files have been modified, deleted, or untracked

```sh
git status
```

### Step 1: Stage changes (Prepare them to be saved)

```sh
git add .          # stages ALL modified and new files

git add filename.js  # stages only one specific file
```

### Step 2: Commit changes (Save the snapshot locally with a clear message)

```sh
git commit -m "feat: add dark mode toggle to navigation bar"

git commit -m "fix: resolve state re-rendering issue in todo item"
```

### Step 3: Push changes (Upload local commits to your online GitHub repository)

```sh
git push origin <branch-name>
```

---

## Setup & Starting Projects

Run these when configuring a new development machine or starting a clean project from scratch.

### Configuration (Only required once per machine setup)

```sh
git config --global user.name "Your Name"

git config --global user.email "your-email@example.com"
```

### Initialize a brand new local repository inside your current folder

```sh
git init
```

### Clone an existing remote repository to your local computer

```sh
git clone <repository-url>
```

---

## Branching & Feature Isolation

Branches let you experiment with design changes, implement new features, or safely upgrade dependencies without breaking your live production website.

### List all local branches (The active branch is marked with an asterisk `*`)

```sh
git branch
```

### Create a new branch but stay on your current branch

```sh
git branch <new-branch-name>
```

### Switch over to an existing branch

```sh
git checkout <branch-name>
```

### Recommended Shortcut: Create a new branch AND switch to it instantly

```sh
git checkout -b <new-branch-name>
```

### Integrate changes from another branch into your active branch

```sh
git merge <branch-name>
```

### Safely delete a branch locally after its code has been merged

```sh
git branch -d <branch-name>
```

---

## Syncing & Collaborative Updates

Use these commands to sync your workspace when changing computers or pulling downstream changes from team members.

### Download latest history from GitHub metadata WITHOUT changing your local code

```sh
git fetch
```

### Download latest changes from GitHub AND automatically merge them into your local branch

```sh
git pull origin <branch-name>
```

---

## Undoing Mistakes & Viewing History

Commands to roll back local mistakes safely before they are permanently pushed upstream.

### View a concise, single-line history log of all past snapshots

```sh
git log --oneline
```

### Unstage a file (Undo `git add` while keeping your actual code modifications intact)

```sh
git reset <file-name>
```

### Discard all local changes in a file, reverting it completely to the last commit

```sh
git checkout -- <file-name>
```

### Completely erase all local uncommitted changes (Use with extreme caution!)

```sh
git reset --hard HEAD
```

---

## Tips for Repositories

- **Meaningful Messages:** Use conventional prefixes in your commits like `feat:` (new feature), `fix:` (bug fix), `docs:` (documentation changes), or `style:` (UI formatting/CSS).
- **The `.gitignore` File:** Always add a `.gitignore` file to your root directory to prevent pushing heavy folders (like `node_modules/`), local environment keys (`.env`), or build logs upstream.
- **GitHub Pages Tip:** Ensure your root web layout file is named exactly `index.html` to allow seamless deployment via GitHub Pages.
