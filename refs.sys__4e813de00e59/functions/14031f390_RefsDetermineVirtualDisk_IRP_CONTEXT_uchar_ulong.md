# RefsDetermineVirtualDisk(_IRP_CONTEXT *,uchar,ulong *)

- ea: `0x14031f390`
- end: `0x14031f9b0`
- name: `?RefsDetermineVirtualDisk@@YAXPEAU_IRP_CONTEXT@@EPEAK@Z`
- size: `1568`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, unsigned __int8, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14031df5c`

## callees

- `0x14000c9b0`
- `0x140085570`
- `0x1400862c0`
- `0x1400d0fd8`
- `0x1401f3fc0`
- `0x1401f4400`
- `0x14028debc`
- `0x14031e740`
- `0x14031f390`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14031f705`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14031f88e`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14031f705`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14031f88e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14031f81d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14031f81d`
- `ntoskrnl!FsRtlGetVirtualDiskNestingLevel` at `0x14031f449`
- `ntoskrnl!FsRtlGetVirtualDiskNestingLevel` at `0x14031f449`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14034371c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140343746`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14034371c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140343746`
- `ntoskrnl!ExReleaseFastResource` at `0x14031f92f`
- `ntoskrnl!ExReleaseFastResource` at `0x14034377a`
- `ntoskrnl!ExReleaseFastResource` at `0x14031f92f`
- `ntoskrnl!ExReleaseFastResource` at `0x14034377a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031f570`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031f962`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403437a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031f570`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031f962`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403437a6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14031f5a1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14031f5a1`

## pseudocode

```c

```
