# OpenCscCplApplet(HWND__ *)

- ea: `0x18000ab1c`
- end: `0x18000abc1`
- name: `?OpenCscCplApplet@@YAKPEAUHWND__@@@Z`
- size: `165`
- prototype: `unsigned int __fastcall(HWND)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000aa80`
- `0x18000d9a0`
- `0x18000da40`

## callees

- `0x180003c20`
- `0x180006360`
- `0x18000ab1c`
- `0x18004c636`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18000ab94`
- `SHELL32!ShellExecuteExW` at `0x18000ab94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab9e`

## string_xrefs

- `0x18000ab36`: `%systemroot%\system32\rundll32.exe`
- `0x18000ab66`: `shell32.dll,Control_RunDLL cscui.dll`

## pseudocode

```c

```
