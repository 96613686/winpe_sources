# MspVolumeCheckpointScan(uchar *)

- ea: `0x1400bea50`
- end: `0x1400bf275`
- name: `?MspVolumeCheckpointScan@@YAXPEAE@Z`
- size: `2085`
- prototype: `void __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400bdee0`

## callees

- `0x140060a4c`
- `0x140082ee0`
- `0x14009cd30`
- `0x1400bea50`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1400bf1ac`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400bf1ac`
- `ntoskrnl!ExQueueWorkItem` at `0x1400bf206`
- `ntoskrnl!ExQueueWorkItem` at `0x1400bf206`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400beaf1`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400bebcd`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400beaf1`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400bebcd`
- `ntoskrnl!DbgPrintEx` at `0x1400bed2c`
- `ntoskrnl!DbgPrintEx` at `0x1400bee16`
- `ntoskrnl!DbgPrintEx` at `0x1400beea5`
- `ntoskrnl!DbgPrintEx` at `0x1400beefd`
- `ntoskrnl!DbgPrintEx` at `0x1400bef59`
- `ntoskrnl!DbgPrintEx` at `0x1400bef9e`
- `ntoskrnl!DbgPrintEx` at `0x1400bf00c`
- `ntoskrnl!DbgPrintEx` at `0x1400bf07f`
- `ntoskrnl!DbgPrintEx` at `0x1400bf125`
- `ntoskrnl!DbgPrintEx` at `0x1400bed2c`
- `ntoskrnl!DbgPrintEx` at `0x1400bee16`
- `ntoskrnl!DbgPrintEx` at `0x1400beea5`
- `ntoskrnl!DbgPrintEx` at `0x1400beefd`
- `ntoskrnl!DbgPrintEx` at `0x1400bef59`
- `ntoskrnl!DbgPrintEx` at `0x1400bef9e`
- `ntoskrnl!DbgPrintEx` at `0x1400bf00c`
- `ntoskrnl!DbgPrintEx` at `0x1400bf07f`
- `ntoskrnl!DbgPrintEx` at `0x1400bf125`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400bead7`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400bebb3`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400bead7`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400bebb3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bf1c0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bf1c0`
- `ntoskrnl!KeClearEvent` at `0x1400bf19c`
- `ntoskrnl!KeClearEvent` at `0x1400bf19c`
- `ntoskrnl!ExReleaseFastResource` at `0x1400beb7f`
- `ntoskrnl!ExReleaseFastResource` at `0x1400bf246`
- `ntoskrnl!ExReleaseFastResource` at `0x1400beb7f`
- `ntoskrnl!ExReleaseFastResource` at `0x1400bf246`

## string_xrefs

- `0x1400beffe`: `ckpt: scheduling after crossing processed delete queue entry count threshold (%d)\n`
- `0x1400bef90`: `ckpt: scheduling due to delete pending being larger than (%d)%%\n`

## pseudocode

```c

```
