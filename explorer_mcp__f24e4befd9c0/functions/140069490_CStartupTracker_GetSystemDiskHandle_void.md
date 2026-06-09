# CStartupTracker::_GetSystemDiskHandle(void)

- ea: `0x140069490`
- end: `0x1400696ec`
- name: `?_GetSystemDiskHandle@CStartupTracker@@AEAAPEAXXZ`
- size: `604`
- prototype: `void *__fastcall(CStartupTracker *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x140090e80`

## callees

- `0x140069490`
- `0x1400696f4`
- `0x14010e160`
- `0x14010ed90`

## import_xrefs

- `ntdll!RtlGetNtSystemRoot` at `0x1400694dd`
- `ntdll!RtlGetNtSystemRoot` at `0x1400694dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400696a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400696bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400696a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400696bd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140069527`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140069603`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140069527`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140069603`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006958c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006966b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006958c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006966b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14006956f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140069654`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14006956f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140069654`

## pseudocode

```c

```
