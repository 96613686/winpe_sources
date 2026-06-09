# CopyFileTransactedA

- ea: `0x18006b700`
- end: `0x18006b79a`
- name: `CopyFileTransactedA`
- size: `154`
- prototype: `BOOL __stdcall(LPCSTR lpExistingFileName, LPCSTR lpNewFileName, LPPROGRESS_ROUTINE lpProgressRoutine, LPVOID lpData, LPBOOL pbCancel, DWORD dwCopyFlags, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x18006b650`
- `0x18006b700`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18006b72e`
- `ntdll!RtlGetCurrentTransaction` at `0x18006b72e`
- `ntdll!RtlSetCurrentTransaction` at `0x18006b743`
- `ntdll!RtlSetCurrentTransaction` at `0x18006b777`
- `ntdll!RtlSetCurrentTransaction` at `0x18006b743`
- `ntdll!RtlSetCurrentTransaction` at `0x18006b777`
- `ntdll!RtlSetLastWin32Error` at `0x18006b784`
- `ntdll!RtlSetLastWin32Error` at `0x18006b784`

## pseudocode

```c

```
