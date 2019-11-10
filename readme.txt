GIT是Linus花了两周时间用C写的一个分布式版本控制系统。
集中式和分布式版本控制系统有什么区别呢？
    1.集中式版本控制系统最大的毛病就是必须联网才能工作
    2.分布式版本控制系统的安全性要高很多
    3.Git极其强大的分支管理

一.安装GIT：https://www.liaoxuefeng.com/wiki/896043488029600/896067074338496
安装完成后，需要在Git Bash设置：
    $ git config --global user.name "Your Name"
    $ git config --global user.email "email@example.com"

二.GIT 操作符
    git add
    git commit -m "commit contxt"
    git status
    git diff filename； 按Q退出git diff
    git log (--pretty=oneline) 产看提交历史 #括号可填可不填
    cat filename: 显示文件内容
    git reset --hard HEAD^ (HEAD表示当前版本，HEAD^表示上一个版本,HEAD^^表示上上一个版本,HEAD~100上100个版本，
                            hard后也可以接版本号commit_id，不需要写全，前几位就可以)
    git reset HEAD filename: 把git add提交的修改撤回
    git reflog: 查看之前的每一次命令
    git checkout -- filename: 丢弃工作区的修改，用版本库里的版本替换工作区的版本
    rm filename: 删除工作区的文件
    git rm filename: 删除版本库中的文件，需要git commit确认删除 


三.GIT远程操作
    创建SSH: ssh-keygen -t rsa -C "youremail@example.com"，一路回车
    登陆GitHub，打开“Account settings”，“SSH Keys”页面：
    点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容
    git remote add origin git@github.com:ylwyjb/GIT
    git remote rm origin:删除远程origin
    git push -u origin master: 第一次本地库推送到远程库
    git push origin master: 后续提交可简化