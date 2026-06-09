# ndisAcquireReadWriteLockX(_NDIS_RW_LOCK *,uchar,_LOCK_STATE *,uchar)

- ea: `0x140034450`
- end: `0x1400346a2`
- name: `?ndisAcquireReadWriteLockX@@YAXPEAU_NDIS_RW_LOCK@@EPEAU_LOCK_STATE@@E@Z`
- size: `594`
- prototype: `void __fastcall(struct _NDIS_RW_LOCK *, unsigned __int8, struct _LOCK_STATE *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400c11e0`

## callees

- `0x140034450`
- `0x1400346b0`
- `0x140034750`
- `0x140046c10`
- `0x1400c1118`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140034470`
- `ntoskrnl!KfRaiseIrql` at `0x140034661`
- `ntoskrnl!KfRaiseIrql` at `0x140034470`
- `ntoskrnl!KfRaiseIrql` at `0x140034661`
- `ntoskrnl!KeTestSpinLock` at `0x1400344ab`
- `ntoskrnl!KeTestSpinLock` at `0x1400344ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140034505`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140034505`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140034617`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140034617`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140034606`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003464e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140034606`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003464e`
- `HAL!KeStallExecutionProcessor` at `0x14003459c`
- `HAL!KeStallExecutionProcessor` at `0x14003459c`

## pseudocode

```c

```
