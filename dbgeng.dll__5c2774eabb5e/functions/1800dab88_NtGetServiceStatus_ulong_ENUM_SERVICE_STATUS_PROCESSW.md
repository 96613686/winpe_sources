# NtGetServiceStatus(ulong *,_ENUM_SERVICE_STATUS_PROCESSW * *)

- ea: `0x1800dab88`
- end: `0x1800dad1a`
- name: `?NtGetServiceStatus@@YAJPEAKPEAPEAU_ENUM_SERVICE_STATUS_PROCESSW@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(unsigned int *, struct _ENUM_SERVICE_STATUS_PROCESSW **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18042361c`
- `0x1804246b0`

## callees

- `0x1800b94c4`
- `0x1800dab88`
- `0x1800daecc`
- `0x18041770c`
- `0x180418c0c`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800dac0e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800dac0e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800dac6c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800dac6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dabb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dabcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dac7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dacbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dacd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dabb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dabcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dac7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dacbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dacd2`

## pseudocode

```c

```
