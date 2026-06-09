# SyncEnumDefaultCompleteDirCallback

- ea: `0x18001c800`
- end: `0x18001cbc4`
- name: `SyncEnumDefaultCompleteDirCallback`
- size: `964`
- prototype: `__int64 __usercall@<rax>(LPVOID lpMem@<rcx>, HANDLE Handle@<rdx>, HANDLE@<r8>, NTSTATUS Status)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c670`

## callees

- `0x18001c800`
- `0x1800360c0`
- `0x180036394`
- `0x18003c460`
- `0x18004fef4`
- `0x180073fe8`

## import_xrefs

- `ntdll!NtClose` at `0x18001c88e`
- `ntdll!NtClose` at `0x18001c8c9`
- `ntdll!NtClose` at `0x18001c88e`
- `ntdll!NtClose` at `0x18001c8c9`
- `ntdll!RtlNtStatusToDosError` at `0x18001c839`
- `ntdll!RtlNtStatusToDosError` at `0x18001c839`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c934`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c934`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c926`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c926`

## string_xrefs

- `0x18001c9a7`: `SyncEnumDefaultCompleteDirCallback: Ctx: 0x%p pHdl: 0x%p sHdl: 0x%p SyncStatus: 0x%x Status: 0x%x`
- `0x18001c96c`: `SyncEnumDefaultCompleteDirCallback: 0x%x`

## pseudocode

```c

```
