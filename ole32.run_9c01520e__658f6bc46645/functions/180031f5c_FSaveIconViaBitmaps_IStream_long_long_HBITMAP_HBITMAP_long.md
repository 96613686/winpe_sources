# _FSaveIconViaBitmaps(IStream *,long,long,HBITMAP__ *,HBITMAP__ *,long *)

- ea: `0x180031f5c`
- end: `0x1800324bc`
- name: `?_FSaveIconViaBitmaps@@YAJPEAUIStream@@JJPEAUHBITMAP__@@1PEAJ@Z`
- size: `1376`
- prototype: `HRESULT __fastcall(IStream *pstm, int xSize, int ySize, HBITMAP__ *hbmpAND, HBITMAP__ *hbmpXOR, int *plLen)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031e80`

## callees

- `0x18001217c`
- `0x180031f5c`
- `0x1800324c4`
- `0x1800324e4`
- `0x180046460`
- `0x1800bda94`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800320bf`
- `KERNELBASE!GlobalAlloc` at `0x1800320bf`
- `KERNELBASE!GlobalFree` at `0x180032272`
- `KERNELBASE!GlobalFree` at `0x180032322`
- `KERNELBASE!GlobalFree` at `0x18003237c`
- `KERNELBASE!GlobalFree` at `0x1800323fc`
- `KERNELBASE!GlobalFree` at `0x180032446`
- `KERNELBASE!GlobalFree` at `0x18003248b`
- `KERNELBASE!GlobalFree` at `0x180032272`
- `KERNELBASE!GlobalFree` at `0x180032322`
- `KERNELBASE!GlobalFree` at `0x18003237c`
- `KERNELBASE!GlobalFree` at `0x1800323fc`
- `KERNELBASE!GlobalFree` at `0x180032446`
- `KERNELBASE!GlobalFree` at `0x18003248b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180032261`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180032311`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18003236b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800323eb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180032435`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18003247a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180032261`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180032311`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18003236b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800323eb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180032435`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18003247a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800320dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800320dc`
- `GDI32!GetDIBits` at `0x180032151`
- `GDI32!GetDIBits` at `0x1800321ac`
- `GDI32!GetDIBits` at `0x180032151`
- `GDI32!GetDIBits` at `0x1800321ac`
- `GDI32!GetDeviceCaps` at `0x180031fe6`
- `GDI32!GetDeviceCaps` at `0x180031ffb`
- `GDI32!GetDeviceCaps` at `0x180031fe6`
- `GDI32!GetDeviceCaps` at `0x180031ffb`
- `USER32!ReleaseDC` at `0x1800322e0`
- `USER32!ReleaseDC` at `0x18003233a`
- `USER32!ReleaseDC` at `0x180032398`
- `USER32!ReleaseDC` at `0x1800322e0`
- `USER32!ReleaseDC` at `0x18003233a`
- `USER32!ReleaseDC` at `0x180032398`
- `USER32!GetDC` at `0x180031fba`
- `USER32!GetDC` at `0x180031fba`

## string_xrefs

- `0x1800322b4`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x1800322fa`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x180032354`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x1800323d4`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x18003241e`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x180032463`: `com\oleaut32\stdtypes\pictobj.cpp`

## pseudocode

```c

```
