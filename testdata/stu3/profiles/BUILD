licenses(["notice"])

package(default_visibility = ["//visibility:public"])

load("//bazel:proto.bzl", "fhir_proto_library")
load("//bazel:protogen.bzl", "gen_fhir_definitions_and_protos")

gen_fhir_definitions_and_protos(
    name = "test",
    additional_proto_imports = [
        "proto/stu3/uscore.proto",
        "proto/stu3/uscore_codes.proto",
    ],
    extensions = [
        "test_extensions.prototxt",
    ],
    package_deps = [
        "//spec:uscore-package",
    ],
    package_info = "test_package_info.prototxt",
    profiles = [
        "test_profiles.prototxt",
    ],
    separate_extensions = True,
)

fhir_proto_library(
    srcs = [
        "test.proto",
        "test_extensions.proto",
    ],
    proto_deps = [
        "//proto/stu3:annotations_proto",
        "//proto/stu3:codes_proto",
        "//proto/stu3:datatypes_proto",
        "//proto/stu3:extensions_proto",
        "//proto/stu3:metadatatypes_proto",
        "//proto/stu3:resources_proto",
        "//proto/stu3:uscore_codes_proto",
        "//proto/stu3:uscore_proto",
    ],
    proto_library_prefix = "test",
)

filegroup(
    name = "testdata",
    srcs = [
        "observation.prototxt",
        "observation-profiled-testobservation.prototxt",
    ],
)
