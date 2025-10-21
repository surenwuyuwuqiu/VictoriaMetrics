windows环境下编译vmctl

# 在仓库根目录
$env:GOOS = "linux"
$env:GOARCH = "amd64"      # 如果目标是 x86_64
$env:CGO_ENABLED = "0"
go mod tidy
go build -ldflags "-s -w" -o vmctl ./app/vmctl
# 产生的 vmctl 是 Linux/amd64 二进制