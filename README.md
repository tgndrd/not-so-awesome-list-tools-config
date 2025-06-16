# Awesome list tools, configs, shortcut

## Bash

### Aliases

List a directory with more informations
> alias ll="ls -al"

List a directory size (folders and subfolders included)
> alias lll="sudo du -h --max-depth=1 | sort -h"

Reload sources
> alias reload-sources="source ~/.bashrc"



### Shortcut

Remove the beginning of the line
> ctrl + u

Remove the end of the line
> ctrl + k

Move the cursor to the end of the line
> ctrl + e

Move the cursor to the beginning of the line
> ctrl + a

Move the cursor one word forward
> alt + f

Move the cursor one word backward
> alt + b

Run the last previous command
> !!

This dummy example shows an usage of `!! `: It will list current directory, then move to `/var` and run `ls -al` in the current directory

```sh
ls -al
cd /var && !!
```

Use the previous argument
> !$

This dummy example shows an usage of `!$`: It will list `/var`, then move to `/var`.

```sh
ls /var
cd !$
```

## Git

### Aliases


```
[alias]
        lga = log --graph --pretty=tformat:'%Cred%h%Creset -%C(cyan)%d %Creset%s %Cgreen(%an %cr)%Creset' --abbrev-commit --all
        co = checkout
        st = status
        br = branch
        cm = commit -m
        ca = commit -a -m 
        cp = cherry-pick
        cb = checkout -b
        rs = reset --soft
        rh = reset --hard
```

### Commands

To push your changes without having to thinks about branch configuration. It will directly push current branch to origin.

```sh
git push origin HEAD
```

Reset last commit

```sh
git reset --soft HEAD~    
```

Amend last commit without editing your commit message
```sh
git commit --amend --no-edit
```

Rebase according to develop, usefull if you are working with atomic commit and want to have a clean commit tree that respect some sort of temporality
```sh
git rebase -i HEAD~$(git rev-list develop..HEAD --count)
```

