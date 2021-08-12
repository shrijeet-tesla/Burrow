load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")
load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix github.com/linkedin/Burrow
gazelle(name = "gazelle")

go_library(
    name = "Burrow_lib",
    srcs = ["main.go"],
    importpath = "github.com/linkedin/Burrow",
    visibility = ["//visibility:private"],
    deps = [
        "//core",
        "@com_github_spf13_viper//:viper",
    ],
)

go_binary(
    name = "Burrow",
    embed = [":Burrow_lib"],
    visibility = ["//visibility:public"],
)

go_test(
    name = "Burrow_test",
    srcs = ["main_test.go"],
    embed = [":Burrow_lib"],
)
