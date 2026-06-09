# CipGetRegistryValueInternal

- ea: `0x180072ab4`
- end: `0x180072c9d`
- name: `CipGetRegistryValueInternal`
- size: `489`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005abe8`
- `0x18007277c`

## callees

- `0x18002bf20`
- `0x18002c080`
- `0x18002c380`
- `0x180072ab4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180072b9d`
- `ntoskrnl!ExAllocatePool2` at `0x180072b9d`
- `ntoskrnl!ZwQueryValueKey` at `0x180072b6c`
- `ntoskrnl!ZwQueryValueKey` at `0x180072bde`
- `ntoskrnl!ZwQueryValueKey` at `0x180072b6c`
- `ntoskrnl!ZwQueryValueKey` at `0x180072bde`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072c67`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072c67`

## pseudocode

```c

```
