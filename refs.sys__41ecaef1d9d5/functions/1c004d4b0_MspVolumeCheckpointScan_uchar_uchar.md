# MspVolumeCheckpointScan(uchar *,uchar *)

- ea: `0x1c004d4b0`
- end: `0x1c004e1c8`
- name: `?MspVolumeCheckpointScan@@YAXPEAE0@Z`
- size: `3352`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1c004d380`

## callees

- `0x1c0037038`
- `0x1c004d1c0`
- `0x1c004d4b0`
- `0x1c004e8a4`
- `0x1c004ef58`
- `0x1c004f008`
- `0x1c0068930`
- `0x1c006a624`
- `0x1c01747f4`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1c004e125`
- `ntoskrnl!KeClearEvent` at `0x1c004e125`
- `ntoskrnl!DbgPrintEx` at `0x1c004dabe`
- `ntoskrnl!DbgPrintEx` at `0x1c004db8a`
- `ntoskrnl!DbgPrintEx` at `0x1c004dbd1`
- `ntoskrnl!DbgPrintEx` at `0x1c004dd70`
- `ntoskrnl!DbgPrintEx` at `0x1c004ddb6`
- `ntoskrnl!DbgPrintEx` at `0x1c004de06`
- `ntoskrnl!DbgPrintEx` at `0x1c004de45`
- `ntoskrnl!DbgPrintEx` at `0x1c004de9c`
- `ntoskrnl!DbgPrintEx` at `0x1c004e023`
- `ntoskrnl!DbgPrintEx` at `0x1c004e0c0`
- `ntoskrnl!DbgPrintEx` at `0x1c004dabe`
- `ntoskrnl!DbgPrintEx` at `0x1c004db8a`
- `ntoskrnl!DbgPrintEx` at `0x1c004dbd1`
- `ntoskrnl!DbgPrintEx` at `0x1c004dd70`
- `ntoskrnl!DbgPrintEx` at `0x1c004ddb6`
- `ntoskrnl!DbgPrintEx` at `0x1c004de06`
- `ntoskrnl!DbgPrintEx` at `0x1c004de45`
- `ntoskrnl!DbgPrintEx` at `0x1c004de9c`
- `ntoskrnl!DbgPrintEx` at `0x1c004e023`
- `ntoskrnl!DbgPrintEx` at `0x1c004e0c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d662`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d6a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d7aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d7f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d8cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d932`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d99a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d662`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d6a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d7aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d7f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d8cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d932`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c004d99a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d72c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d774`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d871`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d8ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d94d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d971`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004da57`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d72c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d774`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d871`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d8ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d94d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004d971`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c004da57`
- `ntoskrnl!ExReleaseFastResource` at `0x1c004e192`
- `ntoskrnl!ExReleaseFastResource` at `0x1c004e192`

## string_xrefs

- `0x1c004de3b`: `ckpt: scheduling due to delete pending being larger than (%d)%%\n`
- `0x1c004de92`: `ckpt: scheduling after crossing processed delete queue entry count threshold (%d)\n`

## pseudocode

```c

```
