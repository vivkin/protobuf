cmake_minimum_required(VERSION 3.0.0)
project(protobuf VERSION 2.6.0)

set(PROTOBUF_LITE_SOURCES
    src/google/protobuf/stubs/atomicops_internals_x86_gcc.cc
    src/google/protobuf/stubs/atomicops_internals_x86_msvc.cc
    src/google/protobuf/stubs/common.cc
    src/google/protobuf/stubs/once.cc
    src/google/protobuf/stubs/hash.h
    src/google/protobuf/stubs/map_util.h
    src/google/protobuf/stubs/shared_ptr.h
    src/google/protobuf/stubs/stringprintf.cc
    src/google/protobuf/stubs/stringprintf.h
    src/google/protobuf/extension_set.cc
    src/google/protobuf/generated_message_util.cc
    src/google/protobuf/message_lite.cc
    src/google/protobuf/repeated_field.cc
    src/google/protobuf/wire_format_lite.cc
    src/google/protobuf/io/coded_stream.cc
    src/google/protobuf/io/coded_stream_inl.h
    src/google/protobuf/io/zero_copy_stream.cc
    src/google/protobuf/io/zero_copy_stream_impl_lite.cc
)

set(PROTOBUF_SOURCES
    src/google/protobuf/stubs/strutil.cc
    src/google/protobuf/stubs/strutil.h
    src/google/protobuf/stubs/substitute.cc
    src/google/protobuf/stubs/substitute.h
    src/google/protobuf/stubs/structurally_valid.cc
    src/google/protobuf/descriptor.cc
    src/google/protobuf/descriptor.pb.cc
    src/google/protobuf/descriptor_database.cc
    src/google/protobuf/dynamic_message.cc
    src/google/protobuf/extension_set_heavy.cc
    src/google/protobuf/generated_message_reflection.cc
    src/google/protobuf/message.cc
    src/google/protobuf/reflection_ops.cc
    src/google/protobuf/service.cc
    src/google/protobuf/text_format.cc
    src/google/protobuf/unknown_field_set.cc
    src/google/protobuf/wire_format.cc
    src/google/protobuf/io/gzip_stream.cc
    src/google/protobuf/io/printer.cc
    src/google/protobuf/io/strtod.cc
    src/google/protobuf/io/tokenizer.cc
    src/google/protobuf/io/zero_copy_stream_impl.cc
    src/google/protobuf/compiler/importer.cc
    src/google/protobuf/compiler/parser.cc
)

set(LIBPROTOC_SOURCES
    src/google/protobuf/compiler/code_generator.cc
    src/google/protobuf/compiler/command_line_interface.cc
    src/google/protobuf/compiler/plugin.cc
    src/google/protobuf/compiler/plugin.pb.cc
    src/google/protobuf/compiler/subprocess.cc
    src/google/protobuf/compiler/subprocess.h
    src/google/protobuf/compiler/zip_writer.cc
    src/google/protobuf/compiler/zip_writer.h
    src/google/protobuf/compiler/cpp/cpp_enum.cc
    src/google/protobuf/compiler/cpp/cpp_enum.h
    src/google/protobuf/compiler/cpp/cpp_enum_field.cc
    src/google/protobuf/compiler/cpp/cpp_enum_field.h
    src/google/protobuf/compiler/cpp/cpp_extension.cc
    src/google/protobuf/compiler/cpp/cpp_extension.h
    src/google/protobuf/compiler/cpp/cpp_field.cc
    src/google/protobuf/compiler/cpp/cpp_field.h
    src/google/protobuf/compiler/cpp/cpp_file.cc
    src/google/protobuf/compiler/cpp/cpp_file.h
    src/google/protobuf/compiler/cpp/cpp_generator.cc
    src/google/protobuf/compiler/cpp/cpp_helpers.cc
    src/google/protobuf/compiler/cpp/cpp_helpers.h
    src/google/protobuf/compiler/cpp/cpp_message.cc
    src/google/protobuf/compiler/cpp/cpp_message.h
    src/google/protobuf/compiler/cpp/cpp_message_field.cc
    src/google/protobuf/compiler/cpp/cpp_message_field.h
    src/google/protobuf/compiler/cpp/cpp_options.h
    src/google/protobuf/compiler/cpp/cpp_primitive_field.cc
    src/google/protobuf/compiler/cpp/cpp_primitive_field.h
    src/google/protobuf/compiler/cpp/cpp_service.cc
    src/google/protobuf/compiler/cpp/cpp_service.h
    src/google/protobuf/compiler/cpp/cpp_string_field.cc
    src/google/protobuf/compiler/cpp/cpp_string_field.h
    src/google/protobuf/compiler/java/java_context.cc
    src/google/protobuf/compiler/java/java_context.h
    src/google/protobuf/compiler/java/java_enum.cc
    src/google/protobuf/compiler/java/java_enum.h
    src/google/protobuf/compiler/java/java_enum_field.cc
    src/google/protobuf/compiler/java/java_enum_field.h
    src/google/protobuf/compiler/java/java_extension.cc
    src/google/protobuf/compiler/java/java_extension.h
    src/google/protobuf/compiler/java/java_field.cc
    src/google/protobuf/compiler/java/java_field.h
    src/google/protobuf/compiler/java/java_file.cc
    src/google/protobuf/compiler/java/java_file.h
    src/google/protobuf/compiler/java/java_generator.cc
    src/google/protobuf/compiler/java/java_generator_factory.cc
    src/google/protobuf/compiler/java/java_generator_factory.h
    src/google/protobuf/compiler/java/java_helpers.cc
    src/google/protobuf/compiler/java/java_helpers.h
    src/google/protobuf/compiler/java/java_lazy_message_field.cc
    src/google/protobuf/compiler/java/java_lazy_message_field.h
    src/google/protobuf/compiler/java/java_message.cc
    src/google/protobuf/compiler/java/java_message.h
    src/google/protobuf/compiler/java/java_message_field.cc
    src/google/protobuf/compiler/java/java_message_field.h
    src/google/protobuf/compiler/java/java_name_resolver.cc
    src/google/protobuf/compiler/java/java_name_resolver.h
    src/google/protobuf/compiler/java/java_primitive_field.cc
    src/google/protobuf/compiler/java/java_primitive_field.h
    src/google/protobuf/compiler/java/java_shared_code_generator.cc
    src/google/protobuf/compiler/java/java_shared_code_generator.h
    src/google/protobuf/compiler/java/java_service.cc
    src/google/protobuf/compiler/java/java_service.h
    src/google/protobuf/compiler/java/java_string_field.cc
    src/google/protobuf/compiler/java/java_string_field.h
    src/google/protobuf/compiler/java/java_doc_comment.cc
    src/google/protobuf/compiler/java/java_doc_comment.h
    src/google/protobuf/compiler/python/python_generator.cc
)

set(PROTOC_SOURCES
    src/google/protobuf/compiler/main.cc
)

add_library(protobuf_lite STATIC ${PROTOBUF_LITE_SOURCES})
target_include_directories(protobuf_lite PUBLIC src ${CMAKE_CURRENT_BINARY_DIR})
if(UNIX)
    target_link_libraries(protobuf_lite pthread)
endif()
add_library(protobuf STATIC ${PROTOBUF_SOURCES})
target_link_libraries(protobuf protobuf_lite)
add_library(libprotoc STATIC ${LIBPROTOC_SOURCES})
target_link_libraries(libprotoc protobuf)
add_executable(protoc ${PROTOC_SOURCES})
target_link_libraries(protoc libprotoc)

if(WIN32)
    configure_file(vsprojects/config.h config.h COPYONLY)
else()
    configure_file(config-unix.h.in config.h COPYONLY)
endif()
