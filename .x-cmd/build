
# local sphere
# specific sphere
# X sphere

(
    target="$1"
    # name transform
    (
        cd "$(x wsroot)"/.sphere
        mkdirp l/j/h/bin "tree.$target/"
    )

    cp -r code "$(x wsroot)/.x-cmd/.sphere/tree.$target/lua/v5.4.6"

    cd "$(x wsroot)/code"
    export CC='zig cc'
    export CPP='zig cpp'
    export RANLIB='zig ranlib'   
    export AR='zig ar' 
    export LIB='zig lib' 

    case "$1" in
        darwin.arm64.default)   # consider renaming
            CC="$CC -target aarch64-macos"
        ;;

        linux.arm64.musl)
            CC="$CC -target aarch64-linux-musl"
        ;;

        win.arm64.mingw)
            CC="$CC -target x86_64-windows-gnu"
        ;;
    esac

    ./configure
    make
    make install "$___X_CMD_"

    # darwin.arm64.0
    # darwin.arm64.0

    # win.arm64.0 => mingw
    # win.x64.0 => mingw
    
    # linux.arm64.0
    # linux.x64.0


)
