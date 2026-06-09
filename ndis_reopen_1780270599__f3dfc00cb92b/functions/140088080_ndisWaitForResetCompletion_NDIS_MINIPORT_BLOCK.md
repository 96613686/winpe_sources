# ndisWaitForResetCompletion(_NDIS_MINIPORT_BLOCK *)

- ea: `0x140088080`
- end: `0x1400881bb`
- name: `?ndisWaitForResetCompletion@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `315`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400410b0`
- `0x1401782c0`

## callees

- `0x140088080`
- `0x140088a2c`
- `0x14015d480`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400880ab`
- `ntoskrnl!KeInitializeEvent` at `0x1400880ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400880f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140088184`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400880f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140088184`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400880bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140088113`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400880bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140088113`
- `HAL!KeStallExecutionProcessor` at `0x140088103`
- `HAL!KeStallExecutionProcessor` at `0x140088103`

## pseudocode

```c

```
