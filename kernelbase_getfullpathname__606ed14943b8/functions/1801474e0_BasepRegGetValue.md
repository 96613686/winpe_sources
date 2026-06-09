# BasepRegGetValue

- ea: `0x1801474e0`
- end: `0x18014778e`
- name: `BasepRegGetValue`
- size: `686`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1801471f0`
- `0x180147320`

## callees

- `0x1801474e0`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18014754e`
- `ntdll!RtlInitUnicodeString` at `0x1801475c1`
- `ntdll!RtlInitUnicodeString` at `0x18014754e`
- `ntdll!RtlInitUnicodeString` at `0x1801475c1`
- `ntdll!NtOpenKey` at `0x180147590`
- `ntdll!NtOpenKey` at `0x180147590`
- `ntdll!RtlNtStatusToDosError` at `0x1801475a2`
- `ntdll!RtlNtStatusToDosError` at `0x1801475a2`
- `ntdll!NtQueryValueKey` at `0x1801475f3`
- `ntdll!NtQueryValueKey` at `0x180147658`
- `ntdll!NtQueryValueKey` at `0x1801475f3`
- `ntdll!NtQueryValueKey` at `0x180147658`
- `ntdll!NtClose` at `0x18014772f`
- `ntdll!NtClose` at `0x18014772f`
- `ntdll!RtlFreeHeap` at `0x180147757`
- `ntdll!RtlFreeHeap` at `0x180147757`
- `ntdll!RtlAllocateHeap` at `0x18014761c`
- `ntdll!RtlAllocateHeap` at `0x18014761c`

## pseudocode

```c

```
