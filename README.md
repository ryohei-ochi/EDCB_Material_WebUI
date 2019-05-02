# 概要
このフォークはライブラリのリスト表示を、更新日時の古い順に並べ替えるカスタマイズしたものになります。  
※グリッド表示はデフォルトの動作です  
  
コンパイルが必要なファイル  
*lua52.dll
*lfs.dll
  
MinGW(gcc)のインストールはこちらを参考にインストールしてください。  
https://webkaru.net/clang/mingw-gcc-install/  
  
※パスの設定を忘れないようにしましょう  
  
luaのソースは公式サイトから取得できます。  
https://www.lua.org/  
  
今回は lua-5.2.4.tar.gz を使用しました。  
  
解凍したソースを、C:\temp\lfs\lua にコピーします。  
  
コンパイル  
cd C:\temp\lfs\lua  
make mingw  
  
LuaFileSystem(lfs.dll)の公式サイトはこちらです。  
https://keplerproject.github.io/luafilesystem/  
  
ソースはGitHubから取得できます。  
https://github.com/keplerproject/luafilesystem  
  
解凍したソースからsrcフォルダを、C:\temp\lfs\lfs にコピーします。  
  
コンパイル  
cd C:\temp\lfs\lfs  
gcc -O2 -c -o src\lfs.o src\lfs.c -Ic:\temp\lfs\lua\src  
gcc -O -shared -o src\lfs.dll src\lfs.o -Lc:\temp\lfs\lua\src -llua52  
  
コンパイルした、lua52.dllとlfs.dllを、EpgTimerSrv.exeとフォルダにコピーします。  
※EpgTimer Serviceを停止してからコピーする必要があります。  
  
後は、本家と同様にファイルを配置して完了です。
