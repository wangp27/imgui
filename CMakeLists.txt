cmake_minimum_required(VERSION 3.20)
project(ImGui LANGUAGES C)

set_target_properties(${LIBRARY_NAME} PROPERTIES POSITION_INDEPENDENT_CODE ON)
if(UNIX AND NOT APPLE)
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -fPIC")
    set(CMAKE_CXX_FLAGS "${CMAKE_C_FLAGS} -Wall -fPIC")
endif()

add_library(${PROJECT_NAME} STATIC
        imconfig.h imgui.cpp imgui.h imgui_draw.cpp imgui_internal.h imgui_tables.cpp
        imgui_widgets.cpp imstb_rectpack.h imstb_textedit.h imstb_truetype.h
        imgui_demo.cpp)

target_include_directories(${PROJECT_NAME} PUBLIC ./)