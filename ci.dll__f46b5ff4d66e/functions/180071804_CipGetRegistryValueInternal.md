# CipGetRegistryValueInternal

- ea: `0x180071804`
- end: `0x1800719ed`
- name: `CipGetRegistryValueInternal`
- size: `489`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180059ed0`
- `0x1800714cc`

## callees

- `0x18002bef0`
- `0x18002c040`
- `0x18002c340`
- `0x180071804`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800718ed`
- `ntoskrnl!ExAllocatePool2` at `0x1800718ed`
- `ntoskrnl!ZwQueryValueKey` at `0x1800718bc`
- `ntoskrnl!ZwQueryValueKey` at `0x18007192e`
- `ntoskrnl!ZwQueryValueKey` at `0x1800718bc`
- `ntoskrnl!ZwQueryValueKey` at `0x18007192e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800719b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800719b7`

## pseudocode

```c

```
