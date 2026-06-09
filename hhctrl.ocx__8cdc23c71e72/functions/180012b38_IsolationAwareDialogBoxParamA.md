# IsolationAwareDialogBoxParamA

- ea: `0x180012b38`
- end: `0x180012bfc`
- name: `IsolationAwareDialogBoxParamA`
- size: `196`
- prototype: `__int64 __fastcall(HINSTANCE hInstance, LPCSTR lpTemplateName, HWND hWndParent, DLGPROC lpDialogFunc, LPARAM)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800123d0`
- `0x1800340b0`
- `0x18004ad98`
- `0x18004c040`
- `0x180059dbc`

## callees

- `0x180002b18`
- `0x180012b38`
- `0x180012c04`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012bd0`
- `KERNEL32!GetLastError` at `0x180012bd0`
- `KERNEL32!DeactivateActCtx` at `0x180012be5`
- `KERNEL32!DeactivateActCtx` at `0x180012be5`
- `KERNEL32!SetLastError` at `0x180012bf1`
- `KERNEL32!SetLastError` at `0x180012bf1`
- `USER32!DialogBoxParamA` at `0x180012ba7`
- `USER32!DialogBoxParamA` at `0x180012ba7`

## pseudocode

```c

```
