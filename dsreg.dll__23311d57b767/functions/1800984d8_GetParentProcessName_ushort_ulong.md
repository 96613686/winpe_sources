# GetParentProcessName(ushort *,ulong)

- ea: `0x1800984d8`
- end: `0x18009865c`
- name: `?GetParentProcessName@@YAJPEAGK@Z`
- size: `388`
- prototype: `__int64 __fastcall(LPWSTR lpExeName, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800aee10`
- `0x1800b0bf8`

## callees

- `0x1800084f4`
- `0x1800307c4`
- `0x1800984d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009853b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009853b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800985a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800985fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800985a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800985fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009862b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009862b`
- `ntdll!NtQueryInformationProcess` at `0x18009855a`
- `ntdll!NtQueryInformationProcess` at `0x18009855a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18009859a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18009859a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800985f0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800985f0`

## string_xrefs

- `0x1800985b7`: `OpenProcess`

## pseudocode

```c

```
