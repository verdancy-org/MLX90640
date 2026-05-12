# CMakeLists.txt for MLX90640

target_include_directories(xr PUBLIC ${CMAKE_CURRENT_LIST_DIR})

target_sources(xr PRIVATE ${CMAKE_CURRENT_LIST_DIR}/MLX90640.cpp)

get_filename_component(_MODULE_DIRNAME ${CMAKE_CURRENT_LIST_DIR} NAME)
set(_DEPS_TARGET "${_MODULE_DIRNAME}_deps")
add_library(${_DEPS_TARGET} INTERFACE)

set_property(GLOBAL APPEND PROPERTY XR_MODULE_DEPS ${_DEPS_TARGET})
