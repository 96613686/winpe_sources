# MspVolumeCheckpointScan(uchar *)

- ea: `0x1400bf710`
- end: `0x1400bff8e`
- name: `?MspVolumeCheckpointScan@@YAXPEAE@Z`
- size: `2174`
- prototype: `void __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400be4c0`

## callees

- `0x140008c40`
- `0x140022ba8`
- `0x1400982e0`
- `0x1400bf710`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1400bfec4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400bfec4`
- `ntoskrnl!ExQueueWorkItem` at `0x1400bff1e`
- `ntoskrnl!ExQueueWorkItem` at `0x1400bff1e`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400bf7b1`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400bf88f`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400bf7b1`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400bf88f`
- `ntoskrnl!DbgPrintEx` at `0x1400bf9ef`
- `ntoskrnl!DbgPrintEx` at `0x1400bfadf`
- `ntoskrnl!DbgPrintEx` at `0x1400bfb73`
- `ntoskrnl!DbgPrintEx` at `0x1400bfbd4`
- `ntoskrnl!DbgPrintEx` at `0x1400bfc36`
- `ntoskrnl!DbgPrintEx` at `0x1400bfc81`
- `ntoskrnl!DbgPrintEx` at `0x1400bfcfc`
- `ntoskrnl!DbgPrintEx` at `0x1400bfd75`
- `ntoskrnl!DbgPrintEx` at `0x1400bfe27`
- `ntoskrnl!DbgPrintEx` at `0x1400bf9ef`
- `ntoskrnl!DbgPrintEx` at `0x1400bfadf`
- `ntoskrnl!DbgPrintEx` at `0x1400bfb73`
- `ntoskrnl!DbgPrintEx` at `0x1400bfbd4`
- `ntoskrnl!DbgPrintEx` at `0x1400bfc36`
- `ntoskrnl!DbgPrintEx` at `0x1400bfc81`
- `ntoskrnl!DbgPrintEx` at `0x1400bfcfc`
- `ntoskrnl!DbgPrintEx` at `0x1400bfd75`
- `ntoskrnl!DbgPrintEx` at `0x1400bfe27`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400bf797`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400bf875`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400bf797`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400bf875`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bfed8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bfed8`
- `ntoskrnl!KeClearEvent` at `0x1400bfeb3`
- `ntoskrnl!KeClearEvent` at `0x1400bfeb3`
- `ntoskrnl!ExReleaseFastResource` at `0x1400bf841`
- `ntoskrnl!ExReleaseFastResource` at `0x1400bff5f`
- `ntoskrnl!ExReleaseFastResource` at `0x1400bf841`
- `ntoskrnl!ExReleaseFastResource` at `0x1400bff5f`

## string_xrefs

- `0x1400bfcee`: `ckpt: scheduling after crossing processed delete queue entry count threshold (%d)\n`
- `0x1400bfc73`: `ckpt: scheduling due to delete pending being larger than (%d)%%\n`

## pseudocode

```c

```
