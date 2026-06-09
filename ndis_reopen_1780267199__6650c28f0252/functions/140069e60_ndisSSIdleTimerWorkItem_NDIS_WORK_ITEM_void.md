# ndisSSIdleTimerWorkItem(_NDIS_WORK_ITEM *,void *)

- ea: `0x140069e60`
- end: `0x140069f98`
- name: `?ndisSSIdleTimerWorkItem@@YAXPEAU_NDIS_WORK_ITEM@@PEAX@Z`
- size: `312`
- prototype: `void(struct _NDIS_WORK_ITEM *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140010d20`
- `0x140069e60`
- `0x140069fa0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140069ec8`
- `ntoskrnl!KeSetEvent` at `0x140069ec8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140069e97`
- `ntoskrnl!KeReleaseSpinLock` at `0x140069edb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140069f7d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140069e97`
- `ntoskrnl!KeReleaseSpinLock` at `0x140069edb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140069f7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140069e7c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140069ea6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140069e7c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140069ea6`

## pseudocode

```c

```
