# CmsVolumeAnalyzer::CompactContainers(CmsTransactionContext *,ulong,uchar *)

- ea: `0x1c00c01e4`
- end: `0x1c00c0582`
- name: `?CompactContainers@CmsVolumeAnalyzer@@QEAAJPEAVCmsTransactionContext@@KPEAE@Z`
- size: `926`
- prototype: `__int64 __fastcall(CmsVolumeAnalyzer *__hidden this, struct CmsTransactionContext *, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1c0052880`
- `0x1c00bf760`

## callees

- `0x1c003fd04`
- `0x1c0053bbc`
- `0x1c0068168`
- `0x1c006ac80`
- `0x1c006af80`
- `0x1c00bfec0`
- `0x1c00c01e4`
- `0x1c00c0b98`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c0237`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c0237`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00c04e8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00c04e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00c0561`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00c0561`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00c0276`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00c0276`
- `HAL!KeQueryPerformanceCounter` at `0x1c00c0284`
- `HAL!KeQueryPerformanceCounter` at `0x1c00c03e8`
- `HAL!KeQueryPerformanceCounter` at `0x1c00c04fe`
- `HAL!KeQueryPerformanceCounter` at `0x1c00c0284`
- `HAL!KeQueryPerformanceCounter` at `0x1c00c03e8`
- `HAL!KeQueryPerformanceCounter` at `0x1c00c04fe`

## pseudocode

```c

```
