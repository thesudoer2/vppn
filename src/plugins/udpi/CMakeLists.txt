cmake_minimum_required(VERSION 3.10)

add_vpp_plugin(udpi_plugin
  SOURCES
    src/dpi.c
    src/dpi_api.c
    src/dpi_cli.c
    src/dpi_node.c
    src/protocols/dpi_ssl.c
  API_FILES
    src/dpi.api
  INSTALL_HEADERS
    src/dpi_app_match.h
    src/dpi.h
  LINK_LIBRARIES
    vlib
    vlibmemory
    vlibapi
    vlibmemoryclient
    vppapiclient
    svm
    vppinfra
    Threads::Threads
    hs
)

add_compile_options(-Wno-unused-function)

message(STATUS ${CMAKE_CURRENT_BINARY_DIR}/src)
include_directories(${CMAKE_CURRENT_BINARY_DIR}/src)