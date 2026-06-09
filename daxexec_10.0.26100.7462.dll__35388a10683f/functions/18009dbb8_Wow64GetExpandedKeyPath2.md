# Wow64GetExpandedKeyPath2

- ea: `0x18009dbb8`
- end: `0x18009dd21`
- name: `Wow64GetExpandedKeyPath2`
- size: `361`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, void *@<rdx>, int, __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800743c0`
- `0x18008b7b0`

## callees

- `0x18009dbb8`
- `0x18009e3cc`
- `0x1800bcd04`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18009dc27`
- `ntdll!RtlNtStatusToDosError` at `0x18009dc82`
- `ntdll!RtlNtStatusToDosError` at `0x18009dc27`
- `ntdll!RtlNtStatusToDosError` at `0x18009dc82`
- `ntdll!RtlAllocateHeap` at `0x18009dc0c`
- `ntdll!RtlAllocateHeap` at `0x18009dc0c`
- `ntdll!RtlFreeHeap` at `0x18009dcf4`
- `ntdll!RtlFreeHeap` at `0x18009dcf4`
- `ntdll!RtlInitUnicodeString` at `0x18009dc4f`
- `ntdll!RtlInitUnicodeString` at `0x18009dc4f`

## pseudocode

```c

```
