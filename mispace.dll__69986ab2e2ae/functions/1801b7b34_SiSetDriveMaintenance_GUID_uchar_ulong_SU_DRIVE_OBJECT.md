# SiSetDriveMaintenance(_GUID *,uchar,ulong,_SU_DRIVE_OBJECT *)

- ea: `0x1801b7b34`
- end: `0x1801b7e22`
- name: `?SiSetDriveMaintenance@@YAHPEAU_GUID@@EKPEAU_SU_DRIVE_OBJECT@@@Z`
- size: `750`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int8, unsigned int, struct _SU_DRIVE_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1801b71d0`

## callees

- `0x180006350`
- `0x180006dd4`
- `0x18000cdb0`
- `0x18019a4a4`
- `0x1801b7b34`
- `0x1801ba570`
- `0x1801ba690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b7d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b7d35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b7bcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b7df3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b7bcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b7df3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b7bb1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b7d49`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b7bb1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b7d49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b7de0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b7de0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b7cc6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b7d1c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b7cc6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b7d1c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b7c78`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b7c78`

## string_xrefs

- `0x1801b7c8f`: `CreateFile`

## pseudocode

```c

```
