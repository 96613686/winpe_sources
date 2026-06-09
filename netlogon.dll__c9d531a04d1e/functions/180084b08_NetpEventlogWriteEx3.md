# NetpEventlogWriteEx3

- ea: `0x180084b08`
- end: `0x180084f5c`
- name: `NetpEventlogWriteEx3`
- size: `1108`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int, int, int, LPCWSTR *, __int16, __int64, size_t Size)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18003f684`

## callees

- `0x180003ac0`
- `0x18000e270`
- `0x18000ed10`
- `0x180084b08`
- `0x180084f64`
- `0x180089aa8`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x180084bf3`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x180084bf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084b72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084b72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084f28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084f28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180084e2d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180084e2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084c57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084c57`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180084e62`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180084e62`
- `ntdll!RtlNtStatusToDosError` at `0x180084bab`
- `ntdll!RtlNtStatusToDosError` at `0x180084bab`

## pseudocode

```c

```
