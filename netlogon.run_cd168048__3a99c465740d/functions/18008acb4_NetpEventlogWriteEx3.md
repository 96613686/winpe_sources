# NetpEventlogWriteEx3

- ea: `0x18008acb4`
- end: `0x18008b133`
- name: `NetpEventlogWriteEx3`
- size: `1151`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int, int, int, LPCWSTR *, __int16, __int64, size_t Size)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180041fbc`

## callees

- `0x180003ce0`
- `0x18000e910`
- `0x18000f3c0`
- `0x18008acb4`
- `0x18008b13c`
- `0x1800901f8`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x18008adab`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x18008adab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008ad1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008ad1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008b0f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008b0f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008aff1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008aff1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ae15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ae15`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008b02c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008b02c`
- `ntdll!RtlNtStatusToDosError` at `0x18008ad5d`
- `ntdll!RtlNtStatusToDosError` at `0x18008ad5d`

## pseudocode

```c

```
