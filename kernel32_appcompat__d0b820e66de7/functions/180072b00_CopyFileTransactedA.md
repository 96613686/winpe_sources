# CopyFileTransactedA

- ea: `0x180072b00`
- end: `0x180072bb3`
- name: `CopyFileTransactedA`
- size: `179`
- prototype: `BOOL __stdcall(LPCSTR lpExistingFileName, LPCSTR lpNewFileName, LPPROGRESS_ROUTINE lpProgressRoutine, LPVOID lpData, LPBOOL pbCancel, DWORD dwCopyFlags, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180072a40`
- `0x180072b00`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180072b2e`
- `ntdll!RtlGetCurrentTransaction` at `0x180072b2e`
- `ntdll!RtlSetCurrentTransaction` at `0x180072b49`
- `ntdll!RtlSetCurrentTransaction` at `0x180072b83`
- `ntdll!RtlSetCurrentTransaction` at `0x180072b49`
- `ntdll!RtlSetCurrentTransaction` at `0x180072b83`
- `ntdll!RtlSetLastWin32Error` at `0x180072b96`
- `ntdll!RtlSetLastWin32Error` at `0x180072b96`

## pseudocode

```c

```
