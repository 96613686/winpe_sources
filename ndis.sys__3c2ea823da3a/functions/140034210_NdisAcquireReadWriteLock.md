# NdisAcquireReadWriteLock

- ea: `0x140034210`
- end: `0x14003443f`
- name: `NdisAcquireReadWriteLock`
- size: `559`
- prototype: `void __stdcall(PNDIS_RW_LOCK Lock, BOOLEAN fWrite, PLOCK_STATE LockState)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140034210`
- `0x1400346b0`
- `0x140034750`
- `0x140046c10`
- `0x1400c1118`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14003422b`
- `ntoskrnl!KfRaiseIrql` at `0x140034372`
- `ntoskrnl!KfRaiseIrql` at `0x14003422b`
- `ntoskrnl!KfRaiseIrql` at `0x140034372`
- `ntoskrnl!KeTestSpinLock` at `0x140034266`
- `ntoskrnl!KeTestSpinLock` at `0x140034266`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400342b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400342b7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400343dd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400343dd`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400343cc`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400343cc`
- `HAL!KeStallExecutionProcessor` at `0x14003435a`
- `HAL!KeStallExecutionProcessor` at `0x14003435a`

## pseudocode

```c

```
