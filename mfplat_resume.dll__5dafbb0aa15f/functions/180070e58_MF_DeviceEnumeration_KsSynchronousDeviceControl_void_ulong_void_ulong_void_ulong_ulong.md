# MF::DeviceEnumeration::KsSynchronousDeviceControl(void *,ulong,void *,ulong,void *,ulong,ulong *)

- ea: `0x180070e58`
- end: `0x180070fac`
- name: `?KsSynchronousDeviceControl@DeviceEnumeration@MF@@YAJPEAXK0K0KPEAK@Z`
- size: `340`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, void *@<rdx>, unsigned int@<r8d>, void *@<r9>, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18006f528`

## callees

- `0x180070e58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180070e94`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180070e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070f41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070f8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070f8d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180070eff`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180070eff`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180070f37`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180070f37`

## pseudocode

```c

```
