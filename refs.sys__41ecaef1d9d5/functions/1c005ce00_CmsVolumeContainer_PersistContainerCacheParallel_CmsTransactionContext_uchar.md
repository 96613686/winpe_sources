# CmsVolumeContainer::PersistContainerCacheParallel(CmsTransactionContext *,uchar)

- ea: `0x1c005ce00`
- end: `0x1c005cf21`
- name: `?PersistContainerCacheParallel@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@E@Z`
- size: `289`
- prototype: `__int64 __fastcall(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1c005cd5c`

## callees

- `0x1c002a708`
- `0x1c00340d4`
- `0x1c005ce00`
- `0x1c005cf30`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c00beb48`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c008cc83`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c008cc83`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c008cdef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c008cdef`
- `ntoskrnl!KeInitializeEvent` at `0x1c005ce94`
- `ntoskrnl!KeInitializeEvent` at `0x1c005ce94`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c008cdde`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c008cdde`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1c005ce48`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1c005ce48`

## pseudocode

```c

```
