# _PictLoadIcon(IStream *,HBITMAP__ * *,HBITMAP__ * *,HICON__ * *,ulong,ulong,ulong)

- ea: `0x18002a6d4`
- end: `0x18002ab5f`
- name: `?_PictLoadIcon@@YAJPEAUIStream@@PEAPEAUHBITMAP__@@1PEAPEAUHICON__@@KKK@Z`
- size: `1163`
- prototype: `HRESULT __fastcall(IStream *pstm, HBITMAP__ **phbmpXor, HBITMAP__ **phbmpAnd, HICON__ **phIcon, unsigned int xSizeDesired, unsigned int ySizeDesired, unsigned int dwFlags)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800be708`

## callees

- `0x18001217c`
- `0x18002a6d4`
- `0x18002ab68`
- `0x18002b620`
- `0x18002c808`
- `0x1800450bc`
- `0x180046460`
- `0x1800b88c8`
- `0x1800b88f8`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18002aa10`
- `KERNELBASE!GlobalAlloc` at `0x18002aa10`
- `KERNELBASE!GlobalFree` at `0x18002aa79`
- `KERNELBASE!GlobalFree` at `0x18002aa79`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002aa66`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002aa66`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002aa39`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002aa39`

## string_xrefs

- `0x18002a790`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x18002a7da`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x18002ab1c`: `com\oleaut32\stdtypes\pictobj.cpp`

## pseudocode

```c

```
