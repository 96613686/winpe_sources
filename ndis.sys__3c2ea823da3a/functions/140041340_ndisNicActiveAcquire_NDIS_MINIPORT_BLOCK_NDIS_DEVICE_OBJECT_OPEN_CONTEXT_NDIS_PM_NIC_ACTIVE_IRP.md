# ndisNicActiveAcquire(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_OBJECT_OPEN_CONTEXT *,_NDIS_PM_NIC_ACTIVE *,_IRP *)

- ea: `0x140041340`
- end: `0x1400416a1`
- name: `?ndisNicActiveAcquire@@YAJPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_DEVICE_OBJECT_OPEN_CONTEXT@@PEAU_NDIS_PM_NIC_ACTIVE@@PEAU_IRP@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_DEVICE_OBJECT_OPEN_CONTEXT *, struct _NDIS_PM_NIC_ACTIVE *, struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14017b220`

## callees

- `0x140014ae0`
- `0x140015170`
- `0x14001cc80`
- `0x140028fb0`
- `0x14003aa40`
- `0x140041340`
- `0x1400416b0`
- `0x140041f40`
- `0x1400422f0`
- `0x140043030`
- `0x14006f150`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400415c6`
- `ntoskrnl!KeCancelTimer` at `0x1400415c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400413f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400414b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400413f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400414b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004137f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004137f`

## pseudocode

```c

```
