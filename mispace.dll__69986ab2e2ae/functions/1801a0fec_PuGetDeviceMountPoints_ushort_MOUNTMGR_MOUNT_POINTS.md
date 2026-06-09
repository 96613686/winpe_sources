# PuGetDeviceMountPoints(ushort *,_MOUNTMGR_MOUNT_POINTS * *)

- ea: `0x1801a0fec`
- end: `0x1801a120f`
- name: `?PuGetDeviceMountPoints@@YAHPEAGPEAPEAU_MOUNTMGR_MOUNT_POINTS@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _MOUNTMGR_MOUNT_POINTS **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x1801a36b4`
- `0x1801a4b20`

## callees

- `0x1800298d0`
- `0x18002b5e4`
- `0x1801a0fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a116d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a116d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a1197`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a11aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a11ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a1197`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a11aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a11ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1020`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a10d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1156`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a11b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1020`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a10d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a1156`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a11b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a104a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a10ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a104a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a10ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a11dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a11dc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a1144`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a1144`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a10b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a10b9`

## string_xrefs

- `0x1801a10a8`: `\\.\MountPointManager`

## pseudocode

```c

```
