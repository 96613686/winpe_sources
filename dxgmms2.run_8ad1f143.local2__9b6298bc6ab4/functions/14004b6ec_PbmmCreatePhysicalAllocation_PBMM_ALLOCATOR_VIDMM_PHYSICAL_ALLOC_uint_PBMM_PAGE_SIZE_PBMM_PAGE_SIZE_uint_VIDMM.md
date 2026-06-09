# PbmmCreatePhysicalAllocation(PBMM_ALLOCATOR *,VIDMM_PHYSICAL_ALLOC *,uint,PBMM_PAGE_SIZE,PBMM_PAGE_SIZE,uint,VIDMM_SEGMENT_PREFERENCES,uint,PBMM_PHYSICAL_ALLOC_FLAGS,PBMM_PHYSICAL_ALLOC * *)

- ea: `0x14004b6ec`
- end: `0x14004b9ed`
- name: `?PbmmCreatePhysicalAllocation@@YAJPEAUPBMM_ALLOCATOR@@PEAUVIDMM_PHYSICAL_ALLOC@@IW4PBMM_PAGE_SIZE@@2IUVIDMM_SEGMENT_PREFERENCES@@ITPBMM_PHYSICAL_ALLOC_FLAGS@@PEAPEAUPBMM_PHYSICAL_ALLOC@@@Z`
- size: `769`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int, unsigned int, unsigned int, __int64, unsigned int, char, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400c69e4`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14004b6ec`
- `0x140058ac0`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x14004b817`
- `watchdog!WdLogSingleEntry2` at `0x14004b817`
- `watchdog!WdLogSingleEntry0` at `0x14004b729`
- `watchdog!WdLogSingleEntry0` at `0x14004b772`
- `watchdog!WdLogSingleEntry0` at `0x14004b7bb`
- `watchdog!WdLogSingleEntry0` at `0x14004b864`
- `watchdog!WdLogSingleEntry0` at `0x14004b94f`
- `watchdog!WdLogSingleEntry0` at `0x14004b9b9`
- `watchdog!WdLogSingleEntry0` at `0x14004b729`
- `watchdog!WdLogSingleEntry0` at `0x14004b772`
- `watchdog!WdLogSingleEntry0` at `0x14004b7bb`
- `watchdog!WdLogSingleEntry0` at `0x14004b864`
- `watchdog!WdLogSingleEntry0` at `0x14004b94f`
- `watchdog!WdLogSingleEntry0` at `0x14004b9b9`
- `watchdog!WdLogSingleEntry1` at `0x14004b99c`
- `watchdog!WdLogSingleEntry1` at `0x14004b99c`

## string_xrefs

- `0x14004b82c`: `Invalid page sizes. Recommend page size must be greater or equal to minimum page size. MinimumPageSize=%u, RecommendedPageSize=%u`

## pseudocode

```c

```
