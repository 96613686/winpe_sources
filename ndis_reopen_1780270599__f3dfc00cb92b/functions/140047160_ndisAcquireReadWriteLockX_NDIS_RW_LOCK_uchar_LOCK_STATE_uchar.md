# ndisAcquireReadWriteLockX(_NDIS_RW_LOCK *,uchar,_LOCK_STATE *,uchar)

- ea: `0x140047160`
- end: `0x1400473b2`
- name: `?ndisAcquireReadWriteLockX@@YAXPEAU_NDIS_RW_LOCK@@EPEAU_LOCK_STATE@@E@Z`
- size: `594`
- prototype: `void __fastcall(struct _NDIS_RW_LOCK *, unsigned __int8, struct _LOCK_STATE *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400c6610`

## callees

- `0x140047160`
- `0x1400473c0`
- `0x140047460`
- `0x14004b5b0`
- `0x1400c6548`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140047180`
- `ntoskrnl!KfRaiseIrql` at `0x140047371`
- `ntoskrnl!KfRaiseIrql` at `0x140047180`
- `ntoskrnl!KfRaiseIrql` at `0x140047371`
- `ntoskrnl!KeTestSpinLock` at `0x1400471bb`
- `ntoskrnl!KeTestSpinLock` at `0x1400471bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140047215`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140047215`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140047316`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14004735e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140047316`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14004735e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140047327`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140047327`
- `HAL!KeStallExecutionProcessor` at `0x1400472ac`
- `HAL!KeStallExecutionProcessor` at `0x1400472ac`

## pseudocode

```c

```
