# Wow64GetExpandedKeyPath2

- ea: `0x18009f550`
- end: `0x18009f69c`
- name: `Wow64GetExpandedKeyPath2`
- size: `332`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, void *@<rdx>, int, __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180075b60`
- `0x18008ce00`

## callees

- `0x18000b132`
- `0x18009f550`
- `0x18009fd24`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18009f5b2`
- `ntdll!RtlNtStatusToDosError` at `0x18009f60d`
- `ntdll!RtlNtStatusToDosError` at `0x18009f5b2`
- `ntdll!RtlNtStatusToDosError` at `0x18009f60d`
- `ntdll!RtlAllocateHeap` at `0x18009f599`
- `ntdll!RtlAllocateHeap` at `0x18009f599`
- `ntdll!RtlFreeHeap` at `0x18009f680`
- `ntdll!RtlFreeHeap` at `0x18009f680`
- `ntdll!RtlInitUnicodeString` at `0x18009f5da`
- `ntdll!RtlInitUnicodeString` at `0x18009f5da`

## pseudocode

```c

```
