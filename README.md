
安装:

```
# 安装tekton
kubectl apply -f release.yaml
由于墙的存在,无法拉取gcr镜像,因此不能直接使用官方release.yaml来安装tekton
项目中的release.yaml替换了官方release文件中的镜像,可直接安装
安装好的tekton默认在tekton-pipelines名字空间下

# 安装tekton-dashboard
kubectl -n tekton-pipelines apply -f tekton-dashboard.yaml
同上
```

Examples:

```
# cd examples
//配置代码源
# kubectl -n tekton-pipelines apply -f tekton_git_resource.yaml
//配置代码仓库认证信息，替换yaml中的username和password
# kubectl -n tekton-pipelines apply -f tekton_git_user.yaml
//配置镜像仓库
# kubectl -n tekton-pipelines apply -f tekton_registry_resource.yaml
//配置镜像仓库认证信息，替换yaml中的username和password
# kubectl -n tekton-pipelines apply -f tekton_registry_user.yaml
//配置k8s的service account 
# kubectl -n tekton-pipelines apply -f tekton_service_account.yaml
//配置tekton中pod权限
# kubectl -n tekton-pipelines apply -f tekton_rbac.yaml
//配置task任务
# kubectl -n tekton-pipelines apply -f tekton_task_build.yaml
//开始执行task
# kubectl -n tekton-pipelines apply -f tekton_task_run.yaml
```

Todo:

```
# 更加复杂的pipeline demo
```
