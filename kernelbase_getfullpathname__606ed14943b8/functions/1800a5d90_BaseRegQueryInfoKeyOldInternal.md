# BaseRegQueryInfoKeyOldInternal

- ea: `0x1800a5d90`
- end: `0x1800a6400`
- name: `BaseRegQueryInfoKeyOldInternal`
- size: `1648`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a5230`
- `0x18011aba0`

## callees

- `0x180061220`
- `0x1800642d8`
- `0x1800a5d90`
- `0x1800a6c40`
- `0x1800a72a8`
- `0x1800a7410`
- `0x1800a78ec`
- `0x1801369c9`
- `0x180136e28`
- `0x180194ec5`
- `0x180194f10`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x1800a60a8`
- `ntdll!NtQuerySecurityObject` at `0x1800a60d8`
- `ntdll!NtQuerySecurityObject` at `0x1800a60a8`
- `ntdll!NtQuerySecurityObject` at `0x1800a60d8`
- `ntdll!RtlNtStatusToDosError` at `0x1800a607d`
- `ntdll!RtlNtStatusToDosError` at `0x1800a63a8`
- `ntdll!RtlNtStatusToDosError` at `0x1800a607d`
- `ntdll!RtlNtStatusToDosError` at `0x1800a63a8`
- `ntdll!NtClose` at `0x1800a626c`
- `ntdll!NtClose` at `0x1800a626c`
- `ntdll!NtQueryKey` at `0x1800a5ef1`
- `ntdll!NtQueryKey` at `0x1800a6361`
- `ntdll!NtQueryKey` at `0x1800a5ef1`
- `ntdll!NtQueryKey` at `0x1800a6361`
- `ntdll!RtlFreeHeap` at `0x1800a6386`
- `ntdll!RtlFreeHeap` at `0x1800a63db`
- `ntdll!RtlFreeHeap` at `0x1800a6386`
- `ntdll!RtlFreeHeap` at `0x1800a63db`
- `ntdll!RtlAllocateHeap` at `0x1800a632f`
- `ntdll!RtlAllocateHeap` at `0x1800a632f`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegQueryInfoKey` at `0x1800a6049`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegQueryInfoKey` at `0x1800a6049`

## pseudocode

```c

```
