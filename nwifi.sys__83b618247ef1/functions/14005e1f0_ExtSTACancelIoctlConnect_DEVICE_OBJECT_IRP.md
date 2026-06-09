# ExtSTACancelIoctlConnect(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14005e1f0`
- end: `0x14005e354`
- name: `?ExtSTACancelIoctlConnect@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `356`
- prototype: `void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140019e34`
- `0x140020870`
- `0x1400208f0`
- `0x14005e0c4`
- `0x14005e1f0`
- `0x14005e694`
- `0x1400630a8`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005e245`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005e245`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e29f`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005e29f`
- `NDIS!NdisReleaseRWLock` at `0x14005e337`
- `NDIS!NdisReleaseRWLock` at `0x14005e337`

## pseudocode

```c

```
