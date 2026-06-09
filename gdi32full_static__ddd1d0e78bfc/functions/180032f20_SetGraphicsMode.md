# SetGraphicsMode

- ea: `0x180032f20`
- end: `0x180033045`
- name: `SetGraphicsMode`
- size: `293`
- prototype: `int __stdcall(HDC hdc, int iMode)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180020a90`
- `0x1800215b0`
- `0x180021b90`
- `0x180024c40`
- `0x180029730`
- `0x180032004`
- `0x180034620`
- `0x180034f78`
- `0x180062a84`
- `0x180079c10`
- `0x18007d830`
- `0x180093bc4`
- `0x1800968a0`
- `0x18009a9e0`

## callees

- `0x180032f20`
- `0x1800756cc`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180032f59`
- `GDI32!GdiGetEntry` at `0x180032f59`
- `GDI32!gW32PID` at `0x180032f97`
- `GDI32!gCookie` at `0x180032fb3`
- `GDI32!gMaxGdiHandleCount` at `0x180032f33`
- `GDI32!GdiSetLastError` at `0x18003302d`
- `GDI32!GdiSetLastError` at `0x18003302d`
- `win32u!NtGdiFlush` at `0x18003300c`
- `win32u!NtGdiFlush` at `0x18003300c`

## pseudocode

```c

```
