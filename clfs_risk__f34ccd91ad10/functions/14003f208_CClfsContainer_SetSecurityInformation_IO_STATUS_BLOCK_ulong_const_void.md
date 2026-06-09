# CClfsContainer::SetSecurityInformation(_IO_STATUS_BLOCK *,ulong const &,void *)

- ea: `0x14003f208`
- end: `0x14003f3bb`
- name: `?SetSecurityInformation@CClfsContainer@@QEAAJPEAU_IO_STATUS_BLOCK@@AEBKPEAX@Z`
- size: `435`
- prototype: `__int64 __fastcall(CClfsContainer *__hidden this, struct _IO_STATUS_BLOCK *, const unsigned int *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14003f1b0`

## callees

- `0x140007470`
- `0x14000f7bc`
- `0x14003f208`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14003f3a8`
- `ntoskrnl!ObfDereferenceObject` at `0x14007cd3d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003f3a8`
- `ntoskrnl!ObfDereferenceObject` at `0x14007cd3d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003f350`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003f350`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003f261`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003f261`
- `ntoskrnl!IoAllocateIrpEx` at `0x14003f279`
- `ntoskrnl!IoAllocateIrpEx` at `0x14003f279`
- `ntoskrnl!IofCallDriver` at `0x14003f330`
- `ntoskrnl!IofCallDriver` at `0x14003f330`
- `ntoskrnl!IoFreeIrp` at `0x14003f38f`
- `ntoskrnl!IoFreeIrp` at `0x14007cd28`
- `ntoskrnl!IoFreeIrp` at `0x14003f38f`
- `ntoskrnl!IoFreeIrp` at `0x14007cd28`

## pseudocode

```c

```
