# RefsDetermineVirtualDisk(_IRP_CONTEXT *,uchar,ulong *)

- ea: `0x14031c2b0`
- end: `0x14031c8d0`
- name: `?RefsDetermineVirtualDisk@@YAXPEAU_IRP_CONTEXT@@EPEAK@Z`
- size: `1568`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, unsigned __int8, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14031ae60`

## callees

- `0x140040410`
- `0x14008c400`
- `0x14008dbd0`
- `0x1400ca788`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x140286ebc`
- `0x14031b640`
- `0x14031c2b0`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14031c625`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14031c7ae`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14031c625`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14031c7ae`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14031c73d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14031c73d`
- `ntoskrnl!FsRtlGetVirtualDiskNestingLevel` at `0x14031c369`
- `ntoskrnl!FsRtlGetVirtualDiskNestingLevel` at `0x14031c369`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14034083c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140340866`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14034083c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140340866`
- `ntoskrnl!ExReleaseFastResource` at `0x14031c84f`
- `ntoskrnl!ExReleaseFastResource` at `0x14034089a`
- `ntoskrnl!ExReleaseFastResource` at `0x14031c84f`
- `ntoskrnl!ExReleaseFastResource` at `0x14034089a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031c490`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031c882`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403408c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031c490`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031c882`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403408c6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14031c4c1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14031c4c1`

## pseudocode

```c

```
