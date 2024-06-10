# Basic Operations

git  init (initialising git)

git add index.html (we can also add multiple files like git add one.html two.html three.html four.html )

git status

git  commit  -m "whatever message you  may  like"

git push origin branchname
# Staging Operations

git diff

git diff filename.php

git show fdc7da2a008448c3af859ed551256a5ba876e7db

git show --name-only fdc7da2a008448c3af859ed551256a5ba876e7db

or

git show fdc7da2a008448c3af859ed551256a5ba876e7db --compact-summary

git diff 7c11b4fd95a652d0838f9c3d19a916e9aeade441 3c0f49c35ab0e6c6f53f22086f323a315e30993d
# Branching

git branch

git checkout -b feature

git push origin feature
# Fetching branch from origin

git fetch --all

git branch -r

git switch remotebranch
# Editing Commits

git commit --amend -m "an updated commit message"

git add hello.py git commit

(Realize you forgot to add the changes from main.py) git add main.py

git commit --amend --no-edit

The --no-edit flag will allow you to make the amendment to your commit without changing its commit message.
# Reverting Files

git restore --staged filename.php
# Reverting Commits

git reset --soft 62634b7af806e9af53a039497c025fdde73841e4 git reset 62634b7af806e9af53a039497c025fdde73841e4 git reset --hard ebbbca3

the above commit id will not be of commit you want to delete , this is the commit id of previos commit that you want to move . the command will keep this commit and delete all commit afterward .

if you do reset soft the changed files will still be added in the green area and you will not have to use git add to add them again , while normal reset will add those files to the untracked files in the red area .
# Deleting branch

git branch -d branchname (if it show error like : The branch 'branchname' is not fully merged use git branch -D ab)

git push origin -d "branchname
# Merging branch

git checkout branchyouwanttomergeinto (you will need to move to branch in which you want to merge) git merge new-branch (this will merge new-branch to the current branch that you are in)
receiving changes from live

fetch all changes to live : git pull origin main

to check which file will come in git pull : git fetch origin main && git diff --name-only main origin/main
# Rollback

git log git checkout 09f0a0d1e322daa445a9ac923f38c30e048cbccb

when fixed then move the head to master by

git checkout master

git pull origin master
# Stash

error: Your local changes to the following files would be overwritten by checkout , Please commit your changes or stash them before you switch branches.

git stash

list git stash list

files git show stash@{0} --stat

single file git diff stash@{1} -- category.php

git show stash@{0} (for all changes)

git stash apply stash@{0}

git stash push MyClass.h MyClass.cpp
# restore specific files from stash

git restore --source=stash@{0} -- app/code/FME/Restrictcustomergroup/etc/frontend/di.xml

git stash drop stash@{0}

To clear the entire stash, run the command git stash clear

git config --global user.email "you@example.com"

git config --global user.name "Your Name"
# practical scenarios

    added a commit and left a file to add
    added the commit altogether to a different branch
    need a commit work from differnt branch

git cherry-pick asdasasdasdasdasddsadsas

git rebase -i HEAD~3 reword squash and other .

git reflog (restore bracnhed , commits)

git reset commitid
