# _FSaveIconViaBitmaps(IStream *,long,long,HBITMAP__ *,HBITMAP__ *,long *)

- ea: `0x18002eb20`
- end: `0x18002efe8`
- name: `?_FSaveIconViaBitmaps@@YAJPEAUIStream@@JJPEAUHBITMAP__@@1PEAJ@Z`
- size: `1224`
- prototype: `HRESULT __fastcall(IStream *pstm, int xSize, int ySize, HBITMAP__ *hbmpAND, HBITMAP__ *hbmpXOR, int *plLen)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002ea58`

## callees

- `0x1800185ec`
- `0x18002eb20`
- `0x18002eff0`
- `0x18002f010`
- `0x180052390`
- `0x1800b5ab8`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18002ec75`
- `KERNELBASE!GlobalAlloc` at `0x18002ec75`
- `KERNELBASE!GlobalFree` at `0x18002ee09`
- `KERNELBASE!GlobalFree` at `0x18002ee9e`
- `KERNELBASE!GlobalFree` at `0x18002eee0`
- `KERNELBASE!GlobalFree` at `0x18002ef44`
- `KERNELBASE!GlobalFree` at `0x18002ef82`
- `KERNELBASE!GlobalFree` at `0x18002efbb`
- `KERNELBASE!GlobalFree` at `0x18002ee09`
- `KERNELBASE!GlobalFree` at `0x18002ee9e`
- `KERNELBASE!GlobalFree` at `0x18002eee0`
- `KERNELBASE!GlobalFree` at `0x18002ef44`
- `KERNELBASE!GlobalFree` at `0x18002ef82`
- `KERNELBASE!GlobalFree` at `0x18002efbb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002edfe`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002ee93`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002eed5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002ef39`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002ef77`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002efb0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002edfe`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002ee93`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002eed5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002ef39`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002ef77`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002efb0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002ec8c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002ec8c`
- `GDI32!GetDIBits` at `0x18002ed05`
- `GDI32!GetDIBits` at `0x18002ed58`
- `GDI32!GetDIBits` at `0x18002ed05`
- `GDI32!GetDIBits` at `0x18002ed58`
- `GDI32!GetDeviceCaps` at `0x18002eb98`
- `GDI32!GetDeviceCaps` at `0x18002eba8`
- `GDI32!GetDeviceCaps` at `0x18002eb98`
- `GDI32!GetDeviceCaps` at `0x18002eba8`
- `USER32!ReleaseDC` at `0x18002ee15`
- `USER32!ReleaseDC` at `0x18002eeaa`
- `USER32!ReleaseDC` at `0x18002eeec`
- `USER32!ReleaseDC` at `0x18002ee15`
- `USER32!ReleaseDC` at `0x18002eeaa`
- `USER32!ReleaseDC` at `0x18002eeec`
- `USER32!GetDC` at `0x18002eb70`
- `USER32!GetDC` at `0x18002eb70`

## string_xrefs

- `0x18002ee4b`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x18002ee7c`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x18002eebe`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x18002ef22`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x18002ef60`: `com\oleaut32\stdtypes\pictobj.cpp`
- `0x18002ef99`: `com\oleaut32\stdtypes\pictobj.cpp`

## pseudocode

```c

```
