# ndisWaitForResetCompletion(_NDIS_MINIPORT_BLOCK *)

- ea: `0x140082e00`
- end: `0x140082f3b`
- name: `?ndisWaitForResetCompletion@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `315`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003e900`
- `0x1401722c0`

## callees

- `0x140082e00`
- `0x1400837ac`
- `0x1401564e0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140082e2b`
- `ntoskrnl!KeInitializeEvent` at `0x140082e2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140082e72`
- `ntoskrnl!KeReleaseSpinLock` at `0x140082f04`
- `ntoskrnl!KeReleaseSpinLock` at `0x140082e72`
- `ntoskrnl!KeReleaseSpinLock` at `0x140082f04`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140082e3b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140082e93`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140082e3b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140082e93`
- `HAL!KeStallExecutionProcessor` at `0x140082e83`
- `HAL!KeStallExecutionProcessor` at `0x140082e83`

## pseudocode

```c

```
