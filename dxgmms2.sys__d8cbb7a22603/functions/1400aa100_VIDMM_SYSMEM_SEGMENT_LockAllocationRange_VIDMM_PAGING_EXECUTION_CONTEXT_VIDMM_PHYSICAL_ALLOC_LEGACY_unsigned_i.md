# VIDMM_SYSMEM_SEGMENT::LockAllocationRange(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,unsigned __int64,unsigned __int64,bool,bool,bool *)

- ea: `0x1400aa100`
- end: `0x1400aa4fc`
- name: `?LockAllocationRange@VIDMM_SYSMEM_SEGMENT@@UEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_K2_N3PEA_N@Z`
- size: `1020`
- prototype: `int(VIDMM_SYSMEM_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, unsigned __int64, unsigned __int64, bool, bool, bool *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops`

## callees

- `0x140004268`
- `0x14003196c`
- `0x140058f50`
- `0x140059030`
- `0x140059080`
- `0x140059380`
- `0x140097b0c`
- `0x1400aa100`
- `0x1400f66d0`
- `0x1400f66f0`
- `0x14010dbac`
- `0x140110ae0`
- `0x14011ac38`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400aa414`
- `watchdog!WdLogSingleEntry3` at `0x1400aa414`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400aa181`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400aa181`
- `watchdog!WdLogSingleEntry0` at `0x1400aa2d2`
- `watchdog!WdLogSingleEntry0` at `0x1400aa393`
- `watchdog!WdLogSingleEntry0` at `0x1400aa2d2`
- `watchdog!WdLogSingleEntry0` at `0x1400aa393`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400aa175`

## string_xrefs

- `0x1400aa30c`: `Encountered a fault trying to copy the user VA into the guaranteed forward progress VA`

## pseudocode

```c

```
