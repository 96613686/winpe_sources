# ExtSTACancelIoctlConnect(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14005fa20`
- end: `0x14005fb84`
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
- `0x14005f8f4`
- `0x14005fa20`
- `0x14005fec4`
- `0x1400648d8`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005fa75`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005fa75`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005facf`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005facf`
- `NDIS!NdisReleaseRWLock` at `0x14005fb67`
- `NDIS!NdisReleaseRWLock` at `0x14005fb67`

## pseudocode

```c

```
