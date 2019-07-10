git

认识git











git的组成

- Workspace：工作区
- Index / Stage：暂存区
- Repository：仓库区（或本地仓库，与HEAD指向的版本对应）
- Remote：远程仓库

注意：git提交的版本是提交的修改的内容，而不是提交一份全新的代码

图解git

指针与分支图形化





git基本操作

本地操作

- add 把工作区的改变提交到暂存区
- commit 把暂存区的缓存提交到本地仓库
- status 查看当前状态
- checkout （HEAD指针，暂存区，工作区）
  - checkout -b [分支名]     在当前分支上开一个新的分支，并且切过去
  - checkout [分支名]  切换到某分支
  - checkout 指定版本位置 将某文件的状态回到指定版本 
- branch
  - branch 列出本地所有分支  -all 列出包括远程仓库的所有分支
  - branch [分支名] 在当前分支上开一个新的分支
  - branch -d [分支名] 删除某分支
- merge
  - merge [分支名]  将指定分支合并到当前分支
- reset （HEAD指针，当前分支指针）
  - reset 指定版本位置 将当前指针，当前分支指针一起回退到某个版本位置
     HEAD^和HEAD~的区别
     
     soft回退指针，mix回退指针+清空暂存区（默认），hard回退指针+清空暂存区+还原工作区（在工作区的改动还没commit时慎用！用作回退版本时使用git reflog查看指针改动）
- .gitignore  
  ` #ingore all the file with '.a' extensions except lib.a 
  ingore all the file in the node_modules folder
  node_modules
  *.a    
  !lib.a`
- stash
  - stash 将当前工作区和暂存区的改变内容缓存起来，通常用于还没提交却需要切换分支的情况
  - stash pop 将之前缓存的内容重新应用到工作区
- revert 回退，但是会产生一个新的commit
- rebase 改变分叉点位置

与远程仓库互动

- clone
- fetch
- pull = fetch + merge
- push
  - push -u origin [分支名]  第一次推到远程仓库时需要关联
