# BasepRegGetValue

- ea: `0x18003379c`
- end: `0x180033a3d`
- name: `BasepRegGetValue`
- size: `673`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180059260`
- `0x180067974`

## callees

- `0x18003379c`
- `0x18007a7d1`
- `0x18007a840`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18003388b`
- `ntdll!NtQueryValueKey` at `0x1800339e6`
- `ntdll!NtQueryValueKey` at `0x18003388b`
- `ntdll!NtQueryValueKey` at `0x1800339e6`
- `ntdll!NtOpenKey` at `0x180033846`
- `ntdll!NtOpenKey` at `0x180033846`
- `ntdll!NtClose` at `0x18003394a`
- `ntdll!NtClose` at `0x18003394a`
- `ntdll!RtlNtStatusToDosError` at `0x1800339f5`
- `ntdll!RtlNtStatusToDosError` at `0x1800339f5`
- `ntdll!RtlInitUnicodeString` at `0x18003380a`
- `ntdll!RtlInitUnicodeString` at `0x180033860`
- `ntdll!RtlInitUnicodeString` at `0x18003380a`
- `ntdll!RtlInitUnicodeString` at `0x180033860`
- `ntdll!RtlFreeHeap` at `0x18003396c`
- `ntdll!RtlFreeHeap` at `0x18003396c`
- `ntdll!RtlAllocateHeap` at `0x1800339b0`
- `ntdll!RtlAllocateHeap` at `0x1800339b0`

## pseudocode

```c

```
