# BasepRegGetValue

- ea: `0x180035a3c`
- end: `0x180035d14`
- name: `BasepRegGetValue`
- size: `728`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18005e990`
- `0x18006e8b4`

## callees

- `0x180035a3c`
- `0x180082751`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180035b3d`
- `ntdll!NtQueryValueKey` at `0x180035cb1`
- `ntdll!NtQueryValueKey` at `0x180035b3d`
- `ntdll!NtQueryValueKey` at `0x180035cb1`
- `ntdll!NtOpenKey` at `0x180035aec`
- `ntdll!NtOpenKey` at `0x180035aec`
- `ntdll!NtClose` at `0x180035c02`
- `ntdll!NtClose` at `0x180035c02`
- `ntdll!RtlNtStatusToDosError` at `0x180035cc6`
- `ntdll!RtlNtStatusToDosError` at `0x180035cc6`
- `ntdll!RtlInitUnicodeString` at `0x180035aaa`
- `ntdll!RtlInitUnicodeString` at `0x180035b0c`
- `ntdll!RtlInitUnicodeString` at `0x180035aaa`
- `ntdll!RtlInitUnicodeString` at `0x180035b0c`
- `ntdll!RtlFreeHeap` at `0x180035c2a`
- `ntdll!RtlFreeHeap` at `0x180035c2a`
- `ntdll!RtlAllocateHeap` at `0x180035c75`
- `ntdll!RtlAllocateHeap` at `0x180035c75`

## pseudocode

```c

```
