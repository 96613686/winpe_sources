# ndisNicActiveAcquire(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_OBJECT_OPEN_CONTEXT *,_NDIS_PM_NIC_ACTIVE *,_IRP *)

- ea: `0x140044540`
- end: `0x1400448a1`
- name: `?ndisNicActiveAcquire@@YAJPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_DEVICE_OBJECT_OPEN_CONTEXT@@PEAU_NDIS_PM_NIC_ACTIVE@@PEAU_IRP@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_DEVICE_OBJECT_OPEN_CONTEXT *, struct _NDIS_PM_NIC_ACTIVE *, struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1401811f0`

## callees

- `0x140010d20`
- `0x14001d110`
- `0x14003e150`
- `0x140044330`
- `0x140044540`
- `0x1400448b0`
- `0x140044c10`
- `0x1400451c0`
- `0x140045f10`
- `0x14005ec80`
- `0x140075090`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400447c6`
- `ntoskrnl!KeCancelTimer` at `0x1400447c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400445f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400446b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400445f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400446b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004457f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004457f`

## pseudocode

```c

```
