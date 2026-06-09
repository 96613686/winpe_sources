# CTSWin32CoreApi::GetDesktopBitmapBitsOnRcv(ITSAsyncResult *,unsigned __int64)

- ea: `0x1804d3af8`
- end: `0x1804d4334`
- name: `?GetDesktopBitmapBitsOnRcv@CTSWin32CoreApi@@AEAAJPEAVITSAsyncResult@@_K@Z`
- size: `2108`
- prototype: `__int64 __fastcall(CTSWin32CoreApi *__hidden this, struct ITSAsyncResult *, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1804d71f0`

## callees

- `0x1800186a0`
- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x18010215c`
- `0x1804d3af8`
- `0x1804d4340`
- `0x1804d51a8`
- `0x180688f26`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804d3c32`
- `KERNEL32!GetLastError` at `0x1804d3d08`
- `KERNEL32!GetLastError` at `0x1804d3c32`
- `KERNEL32!GetLastError` at `0x1804d3d08`
- `USER32!EqualRect` at `0x1804d3e22`
- `USER32!EqualRect` at `0x1804d3e22`
- `USER32!SetRect` at `0x1804d3c28`
- `USER32!SetRect` at `0x1804d3cfe`
- `USER32!SetRect` at `0x1804d3c28`
- `USER32!SetRect` at `0x1804d3cfe`
- `USER32!IsRectEmpty` at `0x1804d3c9a`
- `USER32!IsRectEmpty` at `0x1804d3d52`
- `USER32!IsRectEmpty` at `0x1804d3c9a`
- `USER32!IsRectEmpty` at `0x1804d3d52`
- `USER32!UnionRect` at `0x1804d3dbc`
- `USER32!UnionRect` at `0x1804d3dbc`

## string_xrefs

- `0x1804d405e`: `BitmapCreate failed!`
- `0x1804d3fda`: `SurfaceCreate failed!`
- `0x1804d414f`: `Failed to blt from primary surface onto temp. memory DC surface`

## pseudocode

```c

```
