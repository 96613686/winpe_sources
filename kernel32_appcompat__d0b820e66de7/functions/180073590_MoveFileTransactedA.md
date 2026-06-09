# MoveFileTransactedA

- ea: `0x180073590`
- end: `0x18007363b`
- name: `MoveFileTransactedA`
- size: `171`
- prototype: `BOOL __stdcall(LPCSTR lpExistingFileName, LPCSTR lpNewFileName, LPPROGRESS_ROUTINE lpProgressRoutine, LPVOID lpData, DWORD dwFlags, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x1800277cc`
- `0x180073590`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x1800735be`
- `ntdll!RtlGetCurrentTransaction` at `0x1800735be`
- `ntdll!RtlSetCurrentTransaction` at `0x1800735d9`
- `ntdll!RtlSetCurrentTransaction` at `0x18007360b`
- `ntdll!RtlSetCurrentTransaction` at `0x1800735d9`
- `ntdll!RtlSetCurrentTransaction` at `0x18007360b`
- `ntdll!RtlSetLastWin32Error` at `0x18007361e`
- `ntdll!RtlSetLastWin32Error` at `0x18007361e`

## pseudocode

```c

```
