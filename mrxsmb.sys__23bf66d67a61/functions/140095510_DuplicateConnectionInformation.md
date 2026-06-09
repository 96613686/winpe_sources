# DuplicateConnectionInformation

- ea: `0x140095510`
- end: `0x1400956e6`
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
- `0x140095510`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140095533`
- `ntoskrnl!ExAllocatePool2` at `0x14009558a`
- `ntoskrnl!ExAllocatePool2` at `0x1400955c9`
- `ntoskrnl!ExAllocatePool2` at `0x140095643`
- `ntoskrnl!ExAllocatePool2` at `0x140095533`
- `ntoskrnl!ExAllocatePool2` at `0x14009558a`
- `ntoskrnl!ExAllocatePool2` at `0x1400955c9`
- `ntoskrnl!ExAllocatePool2` at `0x140095643`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095693`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400956ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400956c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095693`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400956ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400956c0`

## pseudocode

```c

```
