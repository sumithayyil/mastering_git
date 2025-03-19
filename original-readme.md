git is distributed version control system
we can edit the code at any time

download webstorm
git config --global user.name ''
git config --global user.email  ''


git init

git config --global init.defaultBranch main
- make the primary branch
  git status - to know the status of commits
- git add readme.md to add the file
- git commit -m 'Add readme.md file' to commit
  to commit all the files together run -  git add ./
- git commit -m 'Add hello and test files'
- git log - to get the history
- each commits have a specific id. so to restore one state copy the id and run
- git checkout 8606d3138a65fd334d2c17c04649fa8383886be1
- no we will get a detached head message that means head is shifted to the previous commit. now we will not see the two js files but it's not deleted
- 'git checkout id ' command will untouch all the logs but only shows the previous state
- git checkout main helps to delete all the broken production



difference between git and github is
git is a tool used to track the changes
github is a cloud platform that allows us to store our git repositories online that allow us to collaborate with others


local repository mean when we run git init a local repo will create in the local machine it will be private until you push in to remote repository
remote repository is a version of your project saved on your server like github
gitlab or bitbucket
on collaborating with a team everyone will have a local repository on the machine and a
remote repo

create  a repo in the github mastering_git and copy the repository origin


run
git branch -M main

to add the local repo to the remote repo
git remote add origin  (we mentioned origin as the repo origin)
git push -u origin main
this will add the local repo to remote repo

Branching and Merging
Branches in git allow us to create different version of your project - we can add different features in to the copied branch. the main version of your
project remain untouched and later merge the branches to the original project
different people can work on different tasks by using branches

To create a new branch

git branch branch-name

to switch to the newly created branch

git checkout branch-name

to move to the main

git checkout main

shortcut to create a new branch and immediately move to it

git checkout -b branch-name( i used feature-branch as branch-name)

very important : when you create a new branch it will be based on the branch that the head is currently on
if you are on the main branch and run the command  git branch branch-name new branch will contain the code
from the main branch at that point in time. however if you are in a different branch with a different code
the new branch will inherit that code instead. so to ensure the correct branch run the code

git branch new-branch-name source-branch


now we are on the feature branch, i added some texts on the readme.md file

run the codes

git add ./
git commit -m ''
-- add a proper commit message like improve mobile responsiveness , Add A/B testing like questioning the answer this commit will bring what changes to the code

so here my commit message will be git commit -m 'Modify readme'

this changes is not showing in the remote repo, so we are not able to see the newly created feature-branch
to publish it

git push --set-upstream origin feature-branch  
upstream branch is a remote branch that your local branch tracks

Alternatively we can use
git push -u origin feature-branch

both will create a upstream branch and establish a tracking relationship with local branch and remote branch

now if you want to push something from the local branch to the remote branch
simply run
git push


if someone made a change
run git pull

so the code will get up-to-date

in the github main branch remain un touched and feature-branch has the modify readme
so, once you made all of the changes to feature-branch and you wanted to merge on to the main branch
to do that open a pull request

a pull request lets you share your changes with your team for review and feedback, once approved and merged
your changes become a part of your main branch

in the github use the compare and pull request button or pull requests menu on nav
select new pull request select main and feature-branch on the next and review the changes
and press create pull request

now the manager can review the code and merge it, if there is no conflicts

you can do it by using code
git merge branch-name (but doing it in github is suggested)

navigate to the main branch and we will be able to see the changes we merged, run
git checkout main

