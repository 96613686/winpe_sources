# VIDMM_SEGMENT::SuspendCpuAccess(VIDMM_PAGING_EXECUTION_CONTEXT *)

- ea: `0x1400cfd94`
- end: `0x1400d012e`
- name: `?SuspendCpuAccess@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z`
- size: `922`
- prototype: `int(VIDMM_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1400ca980`

## callees

- `0x14002faf0`
- `0x14002fbac`
- `0x14002fd70`
- `0x14002fd94`
- `0x1400335c4`
- `0x1400336b8`
- `0x14003ba24`
- `0x14003c554`
- `0x140044dc8`
- `0x140058680`
- `0x140058760`
- `0x14009a958`
- `0x1400cfd94`
- `0x14011f5a8`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d00d1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d00d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d00dd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d00dd`
- `watchdog!WdLogSingleEntry5` at `0x1400cff84`
- `watchdog!WdLogSingleEntry5` at `0x1400d0118`
- `watchdog!WdLogSingleEntry5` at `0x1400cff84`
- `watchdog!WdLogSingleEntry5` at `0x1400d0118`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400cff5e`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400d00f2`

## pseudocode

```c

```
