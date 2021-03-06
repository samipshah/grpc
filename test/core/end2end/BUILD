# Copyright 2016 gRPC authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

load("//bazel:grpc_build_system.bzl", "grpc_cc_library", "grpc_cc_test", "grpc_cc_binary")

licenses(["notice"])  # Apache v2

package(
    features = [
        "-layering_check",
        "-parse_headers",
    ],
)

load(":generate_tests.bzl", "grpc_end2end_tests")

grpc_cc_library(
    name = "cq_verifier",
    srcs = ["cq_verifier.c"],
    hdrs = ["cq_verifier.h"],
    language = "C",
    visibility = ["//test:__subpackages__"],
    deps = [
        "//:gpr",
        "//:grpc",
        "//test/core/util:grpc_test_util",
    ],
)

grpc_cc_library(
    name = "ssl_test_data",
    srcs = [
        "data/client_certs.c",
        "data/server1_cert.c",
        "data/server1_key.c",
        "data/test_root_cert.c",
    ],
    hdrs = ["data/ssl_test_data.h"],
    language = "C",
    visibility = ["//test:__subpackages__"],
)


grpc_cc_library(
    name = "http_proxy",
    srcs = ["fixtures/http_proxy_fixture.c"],
    hdrs = ["fixtures/http_proxy_fixture.h"],
    language = "C",
    deps = [
        "//:gpr",
        "//:grpc",
        "//test/core/util:grpc_test_util",
    ],
)

grpc_cc_library(
    name = "proxy",
    srcs = ["fixtures/proxy.c"],
    hdrs = ["fixtures/proxy.h"],
    language = "C",
    deps = [
        "//:gpr",
        "//:grpc",
        "//test/core/util:grpc_test_util",
    ],
)

grpc_end2end_tests()
