# _GetMUIStringFromCache

- ea: `0x1800e1450`
- end: `0x1800e1762`
- name: `_GetMUIStringFromCache`
- size: `786`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCWSTR SourceString@<rdx>, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180020f20`

## callees

- `0x1800e1450`
- `0x1801369c9`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800e153f`
- `ntdll!RtlInitUnicodeString` at `0x1800e153f`
- `ntdll!RtlNtStatusToDosError` at `0x1800e1660`
- `ntdll!RtlNtStatusToDosError` at `0x1800e1660`
- `ntdll!NtQueryValueKey` at `0x1800e1579`
- `ntdll!NtQueryValueKey` at `0x1800e1710`
- `ntdll!NtQueryValueKey` at `0x1800e1579`
- `ntdll!NtQueryValueKey` at `0x1800e1710`
- `ntdll!RtlFreeHeap` at `0x1800e1630`
- `ntdll!RtlFreeHeap` at `0x1800e1652`
- `ntdll!RtlFreeHeap` at `0x1800e174e`
- `ntdll!RtlFreeHeap` at `0x1800e1630`
- `ntdll!RtlFreeHeap` at `0x1800e1652`
- `ntdll!RtlFreeHeap` at `0x1800e174e`
- `ntdll!RtlAllocateHeap` at `0x1800e150c`
- `ntdll!RtlAllocateHeap` at `0x1800e16c5`
- `ntdll!RtlAllocateHeap` at `0x1800e150c`
- `ntdll!RtlAllocateHeap` at `0x1800e16c5`

## pseudocode

```c

```
