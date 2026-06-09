# CscRegistryMonitorDeleteInstance

- ea: `0x14005402c`
- end: `0x140054119`
- name: `CscRegistryMonitorDeleteInstance`
- size: `237`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140053e28`
- `0x140090740`

## callees

- `0x1400169d4`
- `0x140016a04`
- `0x14005402c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400540d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400540d9`
- `ntoskrnl!ZwClose` at `0x140054097`
- `ntoskrnl!ZwClose` at `0x140054097`
- `ntoskrnl!KeCancelTimer` at `0x140054078`
- `ntoskrnl!KeCancelTimer` at `0x140054078`
- `ntoskrnl!IoFreeWorkItem` at `0x1400540ba`
- `ntoskrnl!IoFreeWorkItem` at `0x1400540ba`

## pseudocode

```c

```
