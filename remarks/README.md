# hello-maven
##数据库在备注remarks中
##注意的部分
###idea从远程git中删除.idea目录

  ####1、将.idea目录加入ignore清单
  .gitignore内容：
  
  /.idea/
  /part00-common/target/
  /part01-lambda/target/
  
  ####2、从git中删除idea
  
  git rm --cached -r .idea
  
 #### 3、将.gitignore文件加入git
  
  git add .gitignore
  
  ####4、提交gitiginore文件，将.idea从源代码仓库中删除
  
  git commit -m "gitignore提交删除.idea"
  
  ####5、push到服务器：把master分支push到远程origin主机
  
  git push origin master
  
  小结的分割线
  小结
  
  gitignore 文件有时候不起作用，其实是有原因的，如下：
  gitignore文件只会ignore未被staged(cached)了的文件，也就是说，已经git add过了，那么就不会忽略了。那么怎么办呢？先请移呀！
  
 #### 注意顺序:
  
  1.删除已经staged/cached的目录或文件(想要忽略的文件);
  2.把gitignore加入stage/cached;
  3.提交.gitignore文件以及所做的修改;
  4.将当前的分支(如master) push 到远程机器 (如origin)
  git rm --cached *.iml
  git add .gitignore
  git commit -m "gitignore提交删除iml" 
  git push origin master
  这里要理解git的四个存储空间：
  
  workspace
  index/stage
  repository
  remote
  可以参考阮一峰这里的这个图，一目了然：常用 Git 命令清单
  workspace: idea里写的代码,保存了就是在workspace工作区;
  index/stage: git add之后会存入stage/index暂存区；
  repository: git commit之后会存入repository本地仓库;
  remote: git push 之后会存入remote远程仓库.
