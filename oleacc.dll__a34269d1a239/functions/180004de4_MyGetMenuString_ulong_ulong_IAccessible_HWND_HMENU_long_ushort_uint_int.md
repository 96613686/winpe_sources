# MyGetMenuString(ulong,ulong,IAccessible *,HWND__ *,HMENU__ *,long,ushort *,uint,int)

- ea: `0x180004de4`
- end: `0x180004f46`
- name: `?MyGetMenuString@@YAHKKPEAUIAccessible@@PEAUHWND__@@PEAUHMENU__@@JPEAGIH@Z`
- size: `354`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct IAccessible *, HWND, HMENU hmenu, int, LPWSTR lpString, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180004c60`
- `0x180035078`

## callees

- `0x180004de4`
- `0x18000619c`
- `0x18001efc4`
- `0x180034f64`
- `0x1800355e4`
- `0x180038644`

## import_xrefs

- `USER32!GetMenuStringW` at `0x180004eec`
- `USER32!GetMenuStringW` at `0x180004eec`
- `USER32!GetMenuItemInfoW` at `0x180004e60`
- `USER32!GetMenuItemInfoW` at `0x180004e60`

## pseudocode

```c

```
