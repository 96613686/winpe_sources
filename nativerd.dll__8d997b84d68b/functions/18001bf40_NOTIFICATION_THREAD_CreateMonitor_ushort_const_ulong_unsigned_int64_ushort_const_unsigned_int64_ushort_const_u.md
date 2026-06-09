# NOTIFICATION_THREAD::CreateMonitor(ushort const *,ulong,unsigned __int64,ushort const *,unsigned __int64,ushort const *,unsigned __int64,void *,int,int,int,CONFIG_MONITOR * *)

- ea: `0x18001bf40`
- end: `0x18001c205`
- name: `?CreateMonitor@NOTIFICATION_THREAD@@QEAAJPEBGK_K0101PEAXHHHPEAPEAUCONFIG_MONITOR@@@Z`
- size: `709`
- prototype: `int(NOTIFICATION_THREAD *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int64, const unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64, void *, int, int, int, struct CONFIG_MONITOR **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800159b4`
- `0x18004ff30`

## callees

- `0x18000aeec`
- `0x18001bf40`
- `0x18001c20c`
- `0x1800412fc`
- `0x180044df0`
- `0x18005102c`
- `0x1800516b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bfca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c104`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bfca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c104`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c112`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c112`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bfdb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bfdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0e7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001c0dd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001c0dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c0af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c0b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c0af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c0b8`

## string_xrefs

- `0x18001c12a`: `NOTIFICATION_THREAD::CreateMonitor`
- `0x18001c15f`: `NOTIFICATION_THREAD::CreateMonitor`

## pseudocode

```c

```
