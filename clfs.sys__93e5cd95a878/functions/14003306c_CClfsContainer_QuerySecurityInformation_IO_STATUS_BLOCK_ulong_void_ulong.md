# CClfsContainer::QuerySecurityInformation(_IO_STATUS_BLOCK *,ulong,void *,ulong &)

- ea: `0x14003306c`
- end: `0x140033245`
- name: `?QuerySecurityInformation@CClfsContainer@@QEAAJPEAU_IO_STATUS_BLOCK@@KPEAXAEAK@Z`
- size: `473`
- prototype: `__int64 __fastcall(CClfsContainer *__hidden this, struct _IO_STATUS_BLOCK *, unsigned int, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003eafc`
- `0x140070b5c`

## callees

- `0x140007470`
- `0x14000f7bc`
- `0x14003306c`
- `0x14003f208`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140033232`
- `ntoskrnl!ObfDereferenceObject` at `0x140033232`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400331c0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400331c0`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400330c3`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400330c3`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400330db`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400330db`
- `ntoskrnl!IofCallDriver` at `0x1400331a0`
- `ntoskrnl!IofCallDriver` at `0x1400331a0`
- `ntoskrnl!IoFreeIrp` at `0x140033219`
- `ntoskrnl!IoFreeIrp` at `0x140033219`

## pseudocode

```c

```
