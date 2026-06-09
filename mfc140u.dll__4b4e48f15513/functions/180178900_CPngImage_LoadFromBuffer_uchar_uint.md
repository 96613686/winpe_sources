# CPngImage::LoadFromBuffer(uchar *,uint)

- ea: `0x180178900`
- end: `0x180178ab3`
- name: `?LoadFromBuffer@CPngImage@@QEAAHPEAEI@Z`
- size: `435`
- prototype: `int __fastcall(CPngImage *this, unsigned __int8 *lpBuffer, unsigned int uiSize)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180178770`

## callees

- `0x1800027e0`
- `0x180089efc`
- `0x18008a2a0`
- `0x180178900`
- `0x1801794e8`
- `0x180231d70`
- `0x1802b09d0`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180178a99`
- `KERNEL32!LeaveCriticalSection` at `0x180178a99`
- `KERNEL32!EnterCriticalSection` at `0x1801789b9`
- `KERNEL32!EnterCriticalSection` at `0x1801789b9`
- `KERNEL32!GlobalAlloc` at `0x180178932`
- `KERNEL32!GlobalAlloc` at `0x180178932`
- `KERNEL32!GlobalLock` at `0x180178943`
- `KERNEL32!GlobalLock` at `0x180178943`
- `KERNEL32!GlobalUnlock` at `0x180178951`
- `KERNEL32!GlobalUnlock` at `0x18017898d`
- `KERNEL32!GlobalUnlock` at `0x180178951`
- `KERNEL32!GlobalUnlock` at `0x18017898d`
- `KERNEL32!GlobalFree` at `0x18017895a`
- `KERNEL32!GlobalFree` at `0x18017895a`
- `VCRUNTIME140!memcpy` at `0x180178984`
- `VCRUNTIME140!memcpy` at `0x180178984`
- `ole32!CreateStreamOnHGlobal` at `0x18017899f`
- `ole32!CreateStreamOnHGlobal` at `0x18017899f`
- `gdiplus!GdipCreateBitmapFromStream` at `0x180178a1a`
- `gdiplus!GdipCreateBitmapFromStream` at `0x180178a1a`
- `gdiplus!GdipDisposeImage` at `0x180178a40`
- `gdiplus!GdipDisposeImage` at `0x180178a40`

## pseudocode

```c

```
