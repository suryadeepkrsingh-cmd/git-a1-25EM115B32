# Assignment 1 - Scenario Answers

## Q1: "nothing added to commit but untracked files present"
- What went wrong: The files were created or modified in the working tree but have not been staged yet. Git only commits changes that are staged into the index.
- What to type next: Run `git add <filename>` (or `git add .` to stage all files), followed by `git commit -m "<message>"`.

## Q2: git diff vs git diff --staged
- git diff: Shows unstaged changes between your working tree and the staging area. For example, before running git add, it showed the updated samosa price and the new items.
- git diff --staged: Shows staged changes between the staging area and the last commit (HEAD). After running git add, it showed the exact modifications ready to be committed.

## Q3: Accidentally committed manager.env before creating .gitignore
- Will adding it to .gitignore now stop tracking it?: No, .gitignore only ignores untracked files. Because Git is already tracking manager.env from the earlier commit, it will continue to track changes to it.
- Command to stop tracking while keeping it on disk:
  git rm --cached manager.env

## Q4: git restore <file> vs git restore --staged <file>
- git restore <file>: Discards unstaged modifications in the working directory, reverting the file back to the staged or HEAD state.
- git restore --staged <file>: Unstages the file from the staging area back to the working directory without deleting the edits from disk.

## Q5: Good commit message vs "update"
- Example rewrite: Rename menu to canteen-menu and delete legacy price sheet
- Why it matters: Descriptive commit messages provide an audit trail and explain the intent behind changes. Writing "update" forces collaborators to read line-by-line diffs to understand what happened and makes debugging with git log difficult.
