# ndisSSIdleTimerWorkItem(_NDIS_WORK_ITEM *,void *)

- ea: `0x140064720`
- end: `0x140064858`
- name: `?ndisSSIdleTimerWorkItem@@YAXPEAU_NDIS_WORK_ITEM@@PEAX@Z`
- size: `312`
- prototype: `void(struct _NDIS_WORK_ITEM *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14001cc80`
- `0x140064720`
- `0x140064860`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140064788`
- `ntoskrnl!KeSetEvent` at `0x140064788`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064757`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006479b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006483d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064757`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006479b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006483d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006473c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064766`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006473c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064766`

## pseudocode

```c

```
