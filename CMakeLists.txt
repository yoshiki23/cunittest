# CMakeのバージョンを設定
cmake_minimum_required(VERSION 2.8.12.2)
# プロジェクト名と使用する言語を設定
project(unitTest_cmake C)

# ./add/include をincludeフォルダに指定
include_directories(./add/include)

# Main という実行ファイルを main.cと add/src/add.c から作成
add_executable(Main main.c add/src/add.c) 

# UnitTest という実行ファイルを test/unitTest.c と add/src/add.c から作成
add_executable(UnitTest test/unitTest.c add/src/add.c)
# unitTest.out作成時に libcunit.aをリンク
target_link_libraries(UnitTest cunit)
