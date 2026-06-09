# CStartupTracker::_GetSystemDiskHandle(void)

- ea: `0x1400661b0`
- end: `0x1400663c9`
- name: `?_GetSystemDiskHandle@CStartupTracker@@AEAAPEAXXZ`
- size: `537`
- prototype: `void *__fastcall(CStartupTracker *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x14008b620`

## callees

- `0x1400661b0`
- `0x1400663d0`
- `0x1401040e0`
- `0x140104ce0`

## import_xrefs

- `ntdll!RtlGetNtSystemRoot` at `0x1400661fd`
- `ntdll!RtlGetNtSystemRoot` at `0x1400661fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006637f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006638c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400663a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006637f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006638c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400663a0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140066241`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14006630a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140066241`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14006630a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006629a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006629a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066366`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140066283`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140066355`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140066283`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140066355`

## pseudocode

```c

```
