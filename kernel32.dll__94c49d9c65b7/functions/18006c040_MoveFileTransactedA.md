# MoveFileTransactedA

- ea: `0x18006c040`
- end: `0x18006c0d2`
- name: `MoveFileTransactedA`
- size: `146`
- prototype: `BOOL __stdcall(LPCSTR lpExistingFileName, LPCSTR lpNewFileName, LPPROGRESS_ROUTINE lpProgressRoutine, LPVOID lpData, DWORD dwFlags, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x18000bb68`
- `0x18006c040`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18006c06e`
- `ntdll!RtlGetCurrentTransaction` at `0x18006c06e`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c083`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c0af`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c083`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c0af`
- `ntdll!RtlSetLastWin32Error` at `0x18006c0bc`
- `ntdll!RtlSetLastWin32Error` at `0x18006c0bc`

## pseudocode

```c

```
