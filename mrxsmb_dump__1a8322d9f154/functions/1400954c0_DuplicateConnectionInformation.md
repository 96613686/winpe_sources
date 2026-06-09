# DuplicateConnectionInformation

- ea: `0x1400954c0`
- end: `0x140095696`
- name: `DuplicateConnectionInformation`
- size: `470`
- prototype: `NTSTATUS __stdcall(PRXCE_CONNECTION_INFORMATION *Copy, PRXCE_CONNECTION_INFORMATION Original, POOL_TYPE PoolType)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140035130`
- `0x14004fe7c`

## callees

- `0x140059f00`
- `0x1400954c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400954e3`
- `ntoskrnl!ExAllocatePool2` at `0x14009553a`
- `ntoskrnl!ExAllocatePool2` at `0x140095579`
- `ntoskrnl!ExAllocatePool2` at `0x1400955f3`
- `ntoskrnl!ExAllocatePool2` at `0x1400954e3`
- `ntoskrnl!ExAllocatePool2` at `0x14009553a`
- `ntoskrnl!ExAllocatePool2` at `0x140095579`
- `ntoskrnl!ExAllocatePool2` at `0x1400955f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095643`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009565c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095670`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095643`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009565c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095670`

## pseudocode

```c

```
