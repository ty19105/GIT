# git基本用法

详见wiki


1.查看添加
— git status  / /查看当前状态
— git add    //工作区向暂存区添加文本文件
    — name   //后跟添加指定文件
    — .      //一次添加完
— git commit  //从暂存区添加到版本区
    —   -m  //后面跟版本的注释
    —  -a -m  //add命令和commit命令一起执行
2.对比
— git diff   //对比工作区和暂存区
— git diff --cached(--staged)   //对比暂存区和版本区   
— git diff master  //对比工作区和版本区域
3.撤销
— git reset HEAD <file.name> //从暂存区撤销到工作区
— git checkout -- <file.name> //撤销工作区的修改到暂存区或版本区的状态，
比如.html文件修改了，
---通过该命令，可以将工作区撤销到版本区的.html状态
— git commit --amend //对提交从新操作，即进行新的提交方案
4.删除
— git rm <file.name>  //rm是remove的缩写，工作区人工删除，需要把暂存区的也删掉，执行该命令达到工作区和暂存区同步
— git rm - -f <file.name>  //工作区暂存区的文件都删除(前提两个区都有该文件)
— git rm --cached <file.name>  //只会删除暂存区文件
5.恢复
— git checkout commit_id <file.name>  //其中commit_id需恢复版本Id，可以不用取完，恢复对应版本指定文件
— git reset --hard commit_id // 恢复整个版本，即多个文件
  —  HEAD^  //HEAD 代表一个指针，指向当前版本版本，“^”代表回到过去的一个版本
  — HEAD~<num>  //一次性回到过去几个版本
—  git reflog  //查找版本，再通过git reset --hard commit_id命令恢复将来想要的版本
6.同步到远程仓库
— git remote    //查看远程仓库
     — -v   //远程操作的项目名字
     — origin   //默认的远程操作的名字
— git push origin master  //本地推送到远程仓库
7.多人协作解决冲突
 — git fetch    //拉去远程仓库，但并不和本地合并
   — Git diff master origin/master  //查看本地区和版本区的区别，
  — Git merge  orgin/master   //有冲突就合并
— git pull     //拉去远程仓库，并且和本地合并，方法较差些
8.开源项目协作（没有权限的操作）以下两个是在github上操作
— fork //开了一个分支或者说克隆了一个版本到当前项目下，相当于通信通道
— pull request //给有权限的人发送一个请求，说明修改了文档。
如果有权限的人仍可了就合并
9.Git分支
— git branch //查看分支
—  git brach <分支> //创建分支 
  — -d   //删除当前分支下的分支
  — -D  //强制删除不在当前分支下的分支
  — --merged   //查看和当前分支合并的分支信息
  — --no-merged  //查看和当前分支合并的分支信息
— git checkout  //检出
  — -b  //检出到新分支,-b是branch的简写
— git merge //合并分支
10.github上的分支
— git push      //git push origin <分支> 意思提交分支到远程仓库
— github上直接创建
11.github上的标签
— git tag
— github上直接创建
