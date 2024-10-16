# Github-Commands

#Steps to Squash Multiple Commits into One:

Fetch the latest changes: Ensure you're working with the latest changes from the remote branch.

git fetch origin

Start an interactive rebase: Use git rebase -i to interactively rebase your commits. Replace N with the number of commits you want to combine.

git rebase -i HEAD~N

For example, if you want to squash the last 3 commits:

git rebase -i HEAD~3

Mark commits for squashing: In the text editor that opens, you'll see a list of your commits, each starting with the word pick. To squash commits, change the word pick to squash (or s) for the commits you want to merge into the previous one. Keep pick for the first commit. Click i to insert and esc to close the insert environment.

For example:

pick 1234567 First commit
squash 2345678 Second commit
squash 3456789 Third commit

Save and exit: After marking the commits, save and close the editor. If you're using Vim, type :wq to save and quit.

Edit the commit message: Git will open another editor allowing you to combine or edit the commit message. Adjust it as needed, then save and close the editor.

Force push the changes: Since you've changed the commit history, you'll need to force push the changes to your branch.

git push --force
