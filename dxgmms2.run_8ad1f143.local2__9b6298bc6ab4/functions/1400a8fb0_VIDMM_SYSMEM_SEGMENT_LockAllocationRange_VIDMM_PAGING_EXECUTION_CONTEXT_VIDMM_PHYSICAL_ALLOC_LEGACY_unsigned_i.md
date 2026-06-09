# VIDMM_SYSMEM_SEGMENT::LockAllocationRange(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,unsigned __int64,unsigned __int64,bool,bool,bool *)

- ea: `0x1400a8fb0`
- end: `0x1400a93ac`
- name: `?LockAllocationRange@VIDMM_SYSMEM_SEGMENT@@UEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_K2_N3PEA_N@Z`
- size: `1020`
- prototype: `int(VIDMM_SYSMEM_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, unsigned __int64, unsigned __int64, bool, bool, bool *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops`

## callees

- `0x1400045ec`
- `0x1400336b8`
- `0x140058680`
- `0x140058760`
- `0x1400587c0`
- `0x140058ac0`
- `0x14009d45c`
- `0x1400a8fb0`
- `0x1400ed9e0`
- `0x1400f16f0`
- `0x1400f1710`
- `0x140109dfc`
- `0x140117138`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400a92c4`
- `watchdog!WdLogSingleEntry3` at `0x1400a92c4`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a9031`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a9031`
- `watchdog!WdLogSingleEntry0` at `0x1400a9182`
- `watchdog!WdLogSingleEntry0` at `0x1400a9243`
- `watchdog!WdLogSingleEntry0` at `0x1400a9182`
- `watchdog!WdLogSingleEntry0` at `0x1400a9243`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a9025`

## string_xrefs

- `0x1400a91bc`: `Encountered a fault trying to copy the user VA into the guaranteed forward progress VA`

## pseudocode

```c

```
