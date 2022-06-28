# nginx-rtmp-win32
원본 소스코드 [이동하기](https://github.com/nginx/nginx)
```
auto/configure \
    --with-cc=cl \
    --builddir=objs \
    --with-debug \
    --prefix= \
    --conf-path=conf/nginx.conf \
    --pid-path=logs/nginx.pid \
    --http-log-path=logs/access.log \
    --error-log-path=logs/error.log \
    --sbin-path=nginx.exe \
    --http-client-body-temp-path=temp/client_body_temp \
    --http-proxy-temp-path=temp/proxy_temp \
    --http-fastcgi-temp-path=temp/fastcgi_temp \
    --http-scgi-temp-path=temp/scgi_temp \
    --http-uwsgi-temp-path=temp/uwsgi_temp \
    --with-cc-opt=-DFD_SETSIZE=1024 \
    --with-pcre=objs/lib/pcre2-10.40 \
    --with-zlib=objs/lib/zlib-1.2.12 \
    --with-http_v2_module \
    --with-http_realip_module \
    --with-http_addition_module \
    --with-http_sub_module \
    --with-http_dav_module  \
    --with-http_stub_status_module \
    --with-http_flv_module \
    --with-http_mp4_module \
    --with-http_gunzip_module \
    --with-http_gzip_static_module \
    --with-http_auth_request_module \
    --with-http_random_index_module \
    --with-http_secure_link_module \
    --with-http_slice_module \
    --with-mail \
    --with-stream \
    --with-openssl=objs/lib/openssl-1_1_1o \
    --with-openssl-opt='no-asm no-tests -D_WIN32_WINNT=0x0501' \
    --with-http_ssl_module \
    --with-mail_ssl_module \
    --with-stream_ssl_module \
    --add-module=objs/lib/nginx-rtmp-module
```
# visual studio 2019 build tools
컴파일 재료
비주얼 스튜디오 2019 빌드 도구 [다운받기](https://my.visualstudio.com/Downloads?q=visual%20studio%202019)
비주얼 스튜디오 2022 소스 수정중

# 컴파일 하기전에
소스코드 풀더/objs/Makefile 파일 열기
```
CFLAGS =  -O2  -W3 -WX -nologo -MT -Zi -Fdobjs/nginx.pdb -DFD_SETSIZE=1024 -DNO_SYS_TYPES_H
```
수정
```
CFLAGS =  -O2  -W3 -nologo -MT -Zi -Fdobjs/nginx.pdb -DFD_SETSIZE=1024 -DNO_SYS_TYPES_H
```
컴파일 하는방법
```
nmake /f objs\MakeFile
```
