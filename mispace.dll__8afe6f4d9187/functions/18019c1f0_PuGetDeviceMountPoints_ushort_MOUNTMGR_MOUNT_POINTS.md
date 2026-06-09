# PuGetDeviceMountPoints(ushort *,_MOUNTMGR_MOUNT_POINTS * *)

- ea: `0x18019c1f0`
- end: `0x18019c3d2`
- name: `?PuGetDeviceMountPoints@@YAHPEAGPEAPEAU_MOUNTMGR_MOUNT_POINTS@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _MOUNTMGR_MOUNT_POINTS **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18019e72c`
- `0x18019faec`

## callees

- `0x18002a948`
- `0x18019c1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c34b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c34b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c36c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c3a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c3b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c36c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c3a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c3b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019c345`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019c387`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019c345`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019c387`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c221`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c2c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c374`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c221`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c2c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c374`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019c247`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019c2e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019c247`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019c2e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019c39a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019c39a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019c326`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019c326`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019c2ac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019c2ac`

## string_xrefs

- `0x18019c29b`: `\\.\MountPointManager`

## pseudocode

```c

```
