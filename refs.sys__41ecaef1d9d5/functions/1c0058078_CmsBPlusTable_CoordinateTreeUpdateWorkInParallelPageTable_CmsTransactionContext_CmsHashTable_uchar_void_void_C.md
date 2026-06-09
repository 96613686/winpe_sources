# CmsBPlusTable::CoordinateTreeUpdateWorkInParallelPageTable(CmsTransactionContext *,CmsHashTable *,uchar,void *,void (CmsBPlusTable::*)(CmsTransactionContext *,void *,ulong,ulong),uchar)

- ea: `0x1c0058078`
- end: `0x1c005813e`
- name: `?CoordinateTreeUpdateWorkInParallelPageTable@CmsBPlusTable@@AEAAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@EPEAXP81@EAAX02KK@ZE@Z`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1c0057ecc`
- `0x1c0057fc8`

## callees

- `0x1c0058078`
- `0x1c006ac80`
- `0x1c00beb48`
- `0x1c00ef210`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c008a34e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c008a34e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c008a390`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c008a514`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c008a390`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c008a514`
- `ntoskrnl!KeInitializeEvent` at `0x1c008a375`
- `ntoskrnl!KeInitializeEvent` at `0x1c008a375`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c008a4bb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c008a4bb`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1c00580ad`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1c00580ad`

## pseudocode

```c

```
