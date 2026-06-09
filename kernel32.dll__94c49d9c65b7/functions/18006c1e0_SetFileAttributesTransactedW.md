# SetFileAttributesTransactedW

- ea: `0x18006c1e0`
- end: `0x18006c248`
- name: `SetFileAttributesTransactedW`
- size: `104`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, DWORD dwFileAttributes, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18006c180`

## callees

- `0x18006c1e0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18006c1fe`
- `ntdll!RtlGetCurrentTransaction` at `0x18006c1fe`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c213`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c229`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c213`
- `ntdll!RtlSetCurrentTransaction` at `0x18006c229`
- `ntdll!RtlSetLastWin32Error` at `0x18006c236`
- `ntdll!RtlSetLastWin32Error` at `0x18006c236`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18006c21f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18006c21f`

## pseudocode

```c

```
