# VidMmReleaseTemporaryResourcesForLegacyAllocation(VIDMM_PHYSICAL_ADAPTER_LEGACY *,VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool)

- ea: `0x140096800`
- end: `0x1400969fe`
- name: `?VidMmReleaseTemporaryResourcesForLegacyAllocation@@YAXPEAUVIDMM_PHYSICAL_ADAPTER_LEGACY@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_N@Z`
- size: `510`
- prototype: `void(struct VIDMM_PHYSICAL_ADAPTER_LEGACY *, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x1400960a8`
- `0x140097408`
- `0x1400982d0`
- `0x1400a0d94`

## callees

- `0x140004268`
- `0x14002d810`
- `0x14002d86c`
- `0x140059030`
- `0x140096800`
- `0x140097b0c`
- `0x140097fd8`
- `0x1400a1bf8`
- `0x140119a4c`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdTrace` at `0x140096833`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140096833`
- `watchdog!WdLogSingleEntry5` at `0x1400969e8`
- `watchdog!WdLogSingleEntry5` at `0x1400969e8`
- `watchdog!WdLogSingleEntry0` at `0x140096932`
- `watchdog!WdLogSingleEntry0` at `0x140096932`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400969c3`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140096815`

## pseudocode

```c

```
