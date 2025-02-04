# GFix: Automatically Fixing Blocking Misuse-of-Channel Bugs 

## Descriptions

GFix aims to automatically fix blocking misuse-of-channel (BMOC) bugs detected by GCatch. It implements three fixing strategies and aims to generate patches with good performance and readability. GFix takes two steps for each input bug. It first applies its dispatcher component to decide whether an input bug can be fixed and if so, which fixing strategy to use. It then invokes one of the three patchers to generate a concrete patch. The technical details of GFix are presented in Section 4 and evaluation results are discussed in Section 5.3 of our ASPLOS paper [1].


## Examples and Demonstrations

1. In the `etcd-example` directory, the `run.sh` script is to download the source code of etcd, change it to a buggy version, and generate three patches using the three fixing strategies for three different bugs detected by GCatch. The details of each bug could be found in the following GitHub links: [bug 1](https://github.com/etcd-io/etcd/pull/11568/commits/b340dfdcbb4be69a07157466634b1e16042aa1a2#diff-3ad06ebe31ef56b10f1c782874d25c414ce13cc8eb381a049bd36be56ea9a969L149), [bug 2](https://github.com/etcd-io/etcd/pull/11568/commits/b340dfdcbb4be69a07157466634b1e16042aa1a2#diff-b7d7aa0bd6404176eb1196324ba19b3fcade68deeef1ab160bcc04b58f8c9341L24), and [bug 3](https://github.com/etcd-io/etcd/pull/11568/commits/b340dfdcbb4be69a07157466634b1e16042aa1a2#diff-b7d7aa0bd6404176eb1196324ba19b3fcade68deeef1ab160bcc04b58f8c9341L45) (the developers did not apply the patch generated for bug 3 directly).

2. In `toy-examples/src` directory, there are three toy programs to demonstrate the three types of bugs that can be fixed by GFix. The `run.sh` script is to apply GFix to the three bugs contained in the three programs. 

## Directories

1. Directory `dispatcher` contains related code for the dispatcher component. 

2. Directory `bmoc-1-patcher` contains code for generating patches using the first fixing strategy. 

3. Directory `bmoc-2-patcher` contains code for generating patches using the second fixing strategy. 

4. Directory `bmoc-3-patcher` contains code for generating patches using the third fixing strategy. 

Please refer to the demonstration scripts to figure out how to use GFix’s code. 


[1] Ziheng Liu, Shuofei Zhu, Boqin Qin, Hao Chen, and Linhai Song. “Automatically Detecting and Fixing Concurrency Bugs in Go Software Systems.” In ASPLOS'2020. 

