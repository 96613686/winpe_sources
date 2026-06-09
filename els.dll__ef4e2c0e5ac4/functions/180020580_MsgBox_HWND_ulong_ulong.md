# MsgBox(HWND__ *,ulong,ulong,...)

- ea: `0x180020580`
- end: `0x18002064f`
- name: `?MsgBox@@YAHPEAUHWND__@@KKZZ`
- size: `207`
- prototype: `__int64(HWND hWnd, UINT uID, unsigned int, ...)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18000688c`
- `0x180007f70`
- `0x18001233c`
- `0x180013370`
- `0x1800135d0`
- `0x180013e60`
- `0x1800152e8`
- `0x180016084`
- `0x18001bfb0`
- `0x180020658`
- `0x180021820`
- `0x180021ff0`

## callees

- `0x180020430`
- `0x1800222d0`

## import_xrefs

- `msvcrt!_vsnwprintf_s` at `0x180020608`
- `msvcrt!_vsnwprintf_s` at `0x180020608`
- `USER32!MessageBoxW` at `0x180020630`
- `USER32!MessageBoxW` at `0x180020630`

## pseudocode

```c

```
