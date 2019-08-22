load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "informer.go",
        "main.go",
    ],
    importpath = "k8s.io/kubernetes/cmd/workload-controller-manager",
    visibility = ["//visibility:private"],
    deps = [
        "//cmd/workload-controller-manager/app:go_default_library",
        "//cmd/workload-controller-manager/app/config:go_default_library",
        "//pkg/cloudfabric-controller/api/types/v1alpha1:go_default_library",
        "//pkg/cloudfabric-controller/clientset/v1alpha1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/runtime:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/wait:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/watch:go_default_library",
        "//staging/src/k8s.io/client-go/kubernetes:go_default_library",
        "//staging/src/k8s.io/client-go/kubernetes/scheme:go_default_library",
        "//staging/src/k8s.io/client-go/rest:go_default_library",
        "//staging/src/k8s.io/client-go/tools/cache:go_default_library",
        "//staging/src/k8s.io/client-go/tools/clientcmd:go_default_library",
        "//staging/src/k8s.io/component-base/logs:go_default_library",
    ],
)

go_binary(
    name = "workload-controller-manager",
    embed = [":go_default_library"],
    visibility = ["//visibility:public"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//cmd/workload-controller-manager/app:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)