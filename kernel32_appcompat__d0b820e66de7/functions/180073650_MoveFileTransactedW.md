# MoveFileTransactedW

- ea: `0x180073650`
- end: `0x180073702`
- name: `MoveFileTransactedW`
- size: `178`
- prototype: `BOOL __stdcall(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, LPPROGRESS_ROUTINE lpProgressRoutine, LPVOID lpData, DWORD dwFlags, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180073650`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18007367e`
- `ntdll!RtlGetCurrentTransaction` at `0x18007367e`
- `ntdll!RtlSetCurrentTransaction` at `0x180073699`
- `ntdll!RtlSetCurrentTransaction` at `0x1800736d2`
- `ntdll!RtlSetCurrentTransaction` at `0x180073699`
- `ntdll!RtlSetCurrentTransaction` at `0x1800736d2`
- `ntdll!RtlSetLastWin32Error` at `0x1800736e5`
- `ntdll!RtlSetLastWin32Error` at `0x1800736e5`
- `KERNELBASE!MoveFileWithProgressTransactedW` at `0x1800736c2`
- `KERNELBASE!MoveFileWithProgressTransactedW` at `0x1800736c2`

## pseudocode

```c

```
