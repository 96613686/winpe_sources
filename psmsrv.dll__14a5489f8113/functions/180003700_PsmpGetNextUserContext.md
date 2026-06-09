# PsmpGetNextUserContext

- ea: `0x180003700`
- end: `0x1800037ed`
- name: `PsmpGetNextUserContext`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002000`
- `0x180002410`
- `0x180002550`
- `0x180016bcc`
- `0x18002a630`
- `0x18002a7d0`
- `0x18002b200`

## callees

- `0x180003700`
- `0x180019c30`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800037de`
- `ntdll!RtlFreeHeap` at `0x1800037de`
- `ntdll!RtlReleaseSRWLockShared` at `0x180003752`
- `ntdll!RtlReleaseSRWLockShared` at `0x180003752`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003765`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003765`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003784`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003784`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000371e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000371e`

## pseudocode

```c

```
