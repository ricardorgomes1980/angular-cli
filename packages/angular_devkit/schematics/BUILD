# Copyright Google Inc. All Rights Reserved.
#
# Use of this source code is governed by an MIT-style license that can be
# found in the LICENSE file at https://angular.io/license
package(default_visibility = ["//visibility:public"])

load("//tools:defaults.bzl", "ts_library")

licenses(["notice"])  # MIT License

ts_library(
    name = "schematics",
    srcs = glob(
        include = ["src/**/*.ts"],
        exclude = [
            "src/**/*_spec.ts",
            "src/**/*_benchmark.ts",
        ],
    ),
    module_name = "@angular-devkit/schematics",
    module_root = "src",
    deps = [
        "//packages/angular_devkit/core",
        "//packages/angular_devkit/core:node",  # TODO: get rid of this for 6.0
        "@rxjs",
        "@rxjs//operators",
        # @typings: node
    ],
)

ts_library(
    name = "tasks",
    srcs = glob(
        include = ["tasks/**/*.ts"],
        exclude = [
            "tasks/**/*_spec.ts",
            "tasks/**/*_benchmark.ts",
        ],
    ),
    module_name = "@angular-devkit/schematics/tasks",
    module_root = "tasks",
    tsconfig = "//:tsconfig.json",
    deps = [
        ":schematics",
        "//packages/angular_devkit/core",
        "//packages/angular_devkit/core:node",
        "@rxjs",
        "@rxjs//operators",
        # @typings: node
        # @typings: tslint
        # @typings: typescript
    ],
)

ts_library(
    name = "tools",
    srcs = glob(
        include = ["tools/**/*.ts"],
        exclude = [
            "tools/**/*_spec.ts",
            "tools/**/*_benchmark.ts",
        ],
    ),
    module_name = "@angular-devkit/schematics/tools",
    module_root = "tools",
    deps = [
        ":schematics",
        ":tasks",
        "//packages/angular_devkit/core",
        "//packages/angular_devkit/core:node",
        "@rxjs",
        "@rxjs//operators",
        # @typings: node
    ],
)

ts_library(
    name = "testing",
    srcs = glob(
        include = ["testing/**/*.ts"],
        exclude = [],
    ),
    module_name = "@angular-devkit/schematics/testing",
    module_root = "testing",
    deps = [
        ":schematics",
        ":tasks",
        ":tools",
        "//packages/angular_devkit/core",
        "@rxjs",
        "@rxjs//operators",
    ],
)

ts_library(
    name = "spec",
    srcs = glob(
        include = ["src/**/*_spec.ts"],
    ),
    deps = [
        ":schematics",
        ":testing",
        "//packages/angular_devkit/core",
        "@rxjs",
        "@rxjs//operators",
        # @typings: jasmine
    ],
)

ts_library(
    name = "tools_spec",
    srcs = glob(
        include = ["tools/**/*_spec.ts"],
    ),
    deps = [
        ":schematics",
        ":tools",
        "//packages/angular_devkit/core",
        "//packages/angular_devkit/core:node",
        "@rxjs",
        "@rxjs//operators",
        # @typings: jasmine
        # @typings: node
    ],
)
