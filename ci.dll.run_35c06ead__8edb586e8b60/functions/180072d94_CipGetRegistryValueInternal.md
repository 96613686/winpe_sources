# CipGetRegistryValueInternal

- ea: `0x180072d94`
- end: `0x180072f7d`
- name: `CipGetRegistryValueInternal`
- size: `489`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005ab10`
- `0x180072a5c`

## callees

- `0x18002c0d0`
- `0x18002c200`
- `0x18002c500`
- `0x180072d94`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180072e7d`
- `ntoskrnl!ExAllocatePool2` at `0x180072e7d`
- `ntoskrnl!ZwQueryValueKey` at `0x180072e4c`
- `ntoskrnl!ZwQueryValueKey` at `0x180072ebe`
- `ntoskrnl!ZwQueryValueKey` at `0x180072e4c`
- `ntoskrnl!ZwQueryValueKey` at `0x180072ebe`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072f47`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072f47`

## pseudocode

```c

```
