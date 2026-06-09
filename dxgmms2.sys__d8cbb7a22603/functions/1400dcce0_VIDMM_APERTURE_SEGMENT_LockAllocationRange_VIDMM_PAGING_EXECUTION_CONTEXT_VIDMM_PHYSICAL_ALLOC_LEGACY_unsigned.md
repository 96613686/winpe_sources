# VIDMM_APERTURE_SEGMENT::LockAllocationRange(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,unsigned __int64,unsigned __int64,bool,bool,bool *)

- ea: `0x1400dcce0`
- end: `0x1400dd09b`
- name: `?LockAllocationRange@VIDMM_APERTURE_SEGMENT@@UEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_K2_N3PEA_N@Z`
- size: `955`
- prototype: `int(VIDMM_APERTURE_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, unsigned __int64, unsigned __int64, bool, bool, bool *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x140004268`
- `0x14003196c`
- `0x140058f50`
- `0x140059030`
- `0x140059080`
- `0x140059380`
- `0x140097b0c`
- `0x1400dcce0`
- `0x1400f66d0`
- `0x1401107c0`
- `0x140110ae0`
- `0x14011ac38`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400dd004`
- `watchdog!WdLogSingleEntry3` at `0x1400dd004`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dcd5f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dcd5f`
- `watchdog!WdLogSingleEntry0` at `0x1400dcec9`
- `watchdog!WdLogSingleEntry0` at `0x1400dcf8b`
- `watchdog!WdLogSingleEntry0` at `0x1400dcec9`
- `watchdog!WdLogSingleEntry0` at `0x1400dcf8b`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400dcd53`

## string_xrefs

- `0x1400dcf03`: `Encountered a fault trying to copy the user VA into the guaranteed forward progress VA.\n`

## pseudocode

```c

```
