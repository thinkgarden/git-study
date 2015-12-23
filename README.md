# git-study
本项目用来练习实践一些git的基本操作。

###常用操作

1、用`git log`可以查看提交历史，以便确定要回退到哪个版本 。简写版`git log —pretty=oneline`

2、用`git reflog`查看命令历史，以便确定要回到未来的哪个版本

3、版本回退

    git reset —hard HEAD^

回退到上一个版本（这里的版本指的是commit到仓库的版本）

4、管理修改

    用 git add 把文件修改添加到暂存区；
    用 git commit 把暂存区的所有内容提交到当前分支。

5、撤销修改
* 当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file

* 当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。

* 已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

6、删除文件

当你从本地删除了一个文件，如果是确实要从版本库中删除该文件，那就用命令`git rm filename`删掉，并且`git commit`;另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本：`git checkout — filename`

`git checkout` 其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。


7、分支创建

    git branch 分支名

8、分支切换

    git checkout 分支名

git checkout 命令加上-b参数表示创建并切换分支

    git checkout -b 分支名


8、分支合并

先切换回需要合并代码的主分支上（通常是master），然后执行

    git merge 分支名

9、删除分支

    git branch -d 分支名

 你可以使用带 -d 选项的 git branch 命令来删除分支
