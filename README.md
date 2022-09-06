
## 
我在使用 iOS 的交叉编译的 golang（不是通过 x/mobile）时遇到了类似的错误，
这个问题是由于我的编译GOOS=darwin而不是GOOS=ios我的编译造成的。
这种行为变化始于https://go-review.googlesource.com/c/go/+/256917/

GOOS=ios 在a413908中引入

对于 x/mobile 仍然使用 GOOS=darwin 
https://github.com/golang/mobile/blob/fea317f4e1ac8a39cd725d852b60936f25f2b23d/cmd/gomobile/env.go#L63-L65