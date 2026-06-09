# CClfsContainer::SetCompression(_IO_STATUS_BLOCK *,uchar)

- ea: `0x140071248`
- end: `0x140071432`
- name: `?SetCompression@CClfsContainer@@AEAAJPEAU_IO_STATUS_BLOCK@@E@Z`
- size: `490`
- prototype: `__int64 __fastcall(CClfsContainer *__hidden this, struct _IO_STATUS_BLOCK *, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140070cd4`

## callees

- `0x140007470`
- `0x14000f7bc`
- `0x140071248`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14007141f`
- `ntoskrnl!ObfDereferenceObject` at `0x14007bdb1`
- `ntoskrnl!ObfDereferenceObject` at `0x14007141f`
- `ntoskrnl!ObfDereferenceObject` at `0x14007bdb1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400713c9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400713c9`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400712aa`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400712aa`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400712c2`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400712c2`
- `ntoskrnl!IofCallDriver` at `0x1400713a9`
- `ntoskrnl!IofCallDriver` at `0x1400713a9`
- `ntoskrnl!IoFreeIrp` at `0x140071403`
- `ntoskrnl!IoFreeIrp` at `0x14007bd99`
- `ntoskrnl!IoFreeIrp` at `0x140071403`
- `ntoskrnl!IoFreeIrp` at `0x14007bd99`

## pseudocode

```c

```
