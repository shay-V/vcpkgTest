cmake_minimum_required(VERSION 3.10)  # 或者您需要的CMake最低版本号
project(HelloWorld)

# 添加源文件路径
set(SOURCE_FILES main.cpp)

# 添加可执行目标
add_executable(${PROJECT_NAME} ${SOURCE_FILES})

# 如果使用C++11及以上特性，可以添加这行
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# 对于Windows系统可能需要添加线程支持
if(WIN32)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /MT")  # 静态链接多线程运行库（如果是Visual Studio编译器）
endif()

# 如果有其他编译选项或者依赖库，也可以在此处添加