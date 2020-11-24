## RJM-GIT-CHEAT-SHEET



#### Config 配置

##### 列出当前配置:

```bash
git config --list
```

##### 列出 repository 配置：

```bash
git config --local --list
```

##### 列出全局配置:

```bash
git config --global --list
```

##### 列出系统配置:

```bash
git config --system --list
```

##### 设置用户名：

```bash
git config --global user.name "jimmy ren"
```

##### 设置用户邮箱：

```bash
git config --global user.email "1824793405@qq.com"
```

##### 设置git命令输出为彩色：

```bash
git config --global color.ui auto
```

##### 设置git使用的文本编辑器：

```bash
git config --global core.editor vim
```



---

#### 配置文件

##### Repository 配置对应的配置文件路径：

```bash
<repo>/.git/config
```

##### 用户全局配置对应的配置文件路径：

```bash
~/.gitconfig # unix based system
```

##### 系统配置对应的配置文件路径：

```bash
/etc/gitconfig
```



---

#### Create 创建

##### 复制一个已经创建的仓库：

```bash
git clone https://github.com/arslanbilal/git-cheat-sheet.git
```

##### 创建一个新的本地仓库：

```bash
git init
```



---

#### 本地修改

##### 显示工作目录下已修改的文件：

```bash
git status
```

##### 显示与上次提交版本文件的不同：

```bash
git diff
```

##### 把当前所有修改添加到下次提交中：

```bash
git add .
```

##### 把对某个文件的修改添加到下次提交中：

```bash
git add -p <file>
```

##### 提交之前已经暂存的变化：

```bash
git commit  # would open default editor for you
```

##### 附加消息提交：

```bash
git commit -m "message here"
```

##### 提交，并将提交时间设置为之前的某个日期:

```bash
git commit --date="`date --date='n day ago'`" -am "commit message"
```

##### 修改上次提交:

```bash
git commit --amend
```

把当前分支中未提交的修改移动到其他分支：

```bash
git stash
git checkout branch2
git stash pop
```

##### 将 stashed changes 应用到当前分支：

```bash
git stash apply
```

##### 删除最新一次的 stashed changes:

```bash
git stash drop
```



---



#### 搜索

##### 从当前目录的所有文件中查找文本内容：

```bash
git grep "hello"
```

在某一版本中搜索文本：

```bash
git grep "hello" v2.5
```



---



#### 提交历史

##### 从最新提交开始，显示所有的提交记录（显示hash，作者信息，提交标题和时间）：

```bash
git log
```

##### 显示所有提交 （仅仅显示提交的hash和message）:

```bash
git log --oneline
```

##### 显示某个用户的所有提交：

```bash
git log --author="username"
```

##### 显示某个文件的所有修改：

```bash
git log -p <file>
```

##### 仅仅显示远端<remote/master> 分支与远端<origin/master>分支提交记录的差集：

```bash
git log --oneline <origin/master> ..<remote/master> --left-right
```

##### 谁，在什么时间，修改了什么文件的内容：

```bash
git blame <file>
```

##### 显示reflog：

```bash
git reflog show
```

##### 删除reflog:

```bash
git reflog delete
```



---



#### 分支与标签

##### 列出所有的分支：

```bash
git branch
```

##### 列出所有的远端分支：

```bash
git branch -r
```

##### 切换分支：

```bash
git checkout <branch>
```

##### 创建并切换到新分支：

```bash
git checkout -b <branch>
```

##### 基于当前分支创建新分支：

```bash
git branch <new-branch>
```

##### 基于远程分支创建新的可追溯的分支：

```bash
git branch --track <new-branch> <remote-branch>
```

##### 删除本地分支：

```bash
git branch -d <branch>
```

##### 强制删除一个本地分支：

```bash
git branch -D <branch>
```

##### 给当前版本打标签：

```bash
git tag <tag-name>
```

##### 给当前版本打标签并附加消息：

```bash
git tag -a <tag-name>
```



---



#### 更新与发布

##### 列出当前配置的远程端：

```bash
git remote -v
```

##### 显示远程端的信息：

```bash
git remote show <remote>
```

##### 添加新的远程端：

```bash
git remote add <remote> <url>
```

##### 下载远程版本，但不合并到HEAD中：

```bash
git fetch <remote>
```

##### 下载远程版本，并自动与HEAD版本合并：

```bash
git remote pull <remote> <url>
```

##### 将远程端版本合并到本地版本中：

```bash
git pull origin master
```

##### 以 rebase 方式将远端分支与本地合并：

```bash
git pull --rebase <remote>  <branch>
```

##### 将本地版本发布到远程端：

```bash
git push remote <remote> <branch>
```

##### 删除远程端分支：

```bash
git push <remote> :<branch>
or
git push <remote> --delete <branch>
```

##### 发布标签：

```bash
git push --tags
```



---



#### 撤销

##### 放弃工作目录下的所有修改：

```bash
git reset --hard HEAD
```

##### 移除缓存区的所有文件（撤销上次 git add）：

```bash
git reset HEAD
```

##### 放弃某个文件的所有本地修改：

```bash
git checkout HEAD <file>
```

##### 重置一个提交（通过创建一个截然不同的新提交）:

```bash
git revert <commit>
```

##### 将HEAD重置到指定的版本，并抛弃该版本之后的所有修改：

```bash
git reset --hard <commit>
```

##### 用远端分支强制覆盖本地分支：

```bash
git reset --hard <remote/branch> e.g., upstream/master, origin/my-feature
```

##### 删除添加 .gitignore 文件前错误提交的文件：

```bash
git rm -r --cached .
git add .
git commit -m "remove xyz file and modify .gitignore file"
```



[MORE](https://github.com/arslanbilal/git-cheat-sheet/blob/master/other-sheets/git-cheat-sheet-zh.md#%E9%85%8D%E7%BD%AE)