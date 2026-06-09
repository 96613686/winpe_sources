# RemoveDirectoryTransactedW

- ea: `0x18006bb40`
- end: `0x18006bbb7`
- name: `RemoveDirectoryTransactedW`
- size: `119`
- prototype: `BOOL __stdcall(LPCWSTR lpPathName, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18005ddd0`

## callees

- `0x18006bb40`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18006bb5f`
- `ntdll!RtlGetCurrentTransaction` at `0x18006bb5f`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bb7c`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bb90`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bb7c`
- `ntdll!RtlSetCurrentTransaction` at `0x18006bb90`
- `ntdll!RtlSetLastWin32Error` at `0x18006bb71`
- `ntdll!RtlSetLastWin32Error` at `0x18006bb9d`
- `ntdll!RtlSetLastWin32Error` at `0x18006bb71`
- `ntdll!RtlSetLastWin32Error` at `0x18006bb9d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006bb86`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006bb86`

## pseudocode

```c

```
