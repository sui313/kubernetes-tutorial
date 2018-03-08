#### arrange

在容器环境中，编排通常涉及到三个方面:

资源编排 - 负责资源的分配，如限制 namespace 的可用资源，scheduler 针对资源的不同调度策略； 

工作负载编排 - 负责在资源之间共享工作负载，如 Kubernetes 通过不同的 controller 将 Pod 调度到合适的 node 上，并且负责管理它们的生命周期；

服务编排 - 负责服务发现和高可用等，如 Kubernetes 中可用通过 Service 来对内暴露服务，通过 Ingress 来对外暴露服务。

在 Kubernetes 中有 5 种我们经常会用到的控制器来帮助我们进行容器编排，它们分别是 Deployment, StatefulSet, DaemonSet, CronJob, Job。

在这 5 种常见资源中，Deployment 经常被作为无状态实例控制器使用; StatefulSet 是一个有状态实例控制器;  DaemonSet 可以指定在选定的 Node 上跑，每个 Node 上会跑一个副本，它有一个特点是它的 Pod 的调度不经过调度器，在 Pod 创建的时候就直接绑定 NodeName；
最后一个是定时任务，它是一个上级控制器，和 Deployment 有些类似，当一个定时任务触发的时候，它会去创建一个 Job ，具体的任务实际上是由 Job 来负责执行的。他们之间的关系如下图：
<p align="center">
<img width="700" align="center" src="../images/9.jpg" />
</p>













































License
This is free software distributed under the terms of the MIT license