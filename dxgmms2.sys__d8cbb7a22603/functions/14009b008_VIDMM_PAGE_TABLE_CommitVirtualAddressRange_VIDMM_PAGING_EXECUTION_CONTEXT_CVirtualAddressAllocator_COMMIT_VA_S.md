# VIDMM_PAGE_TABLE::CommitVirtualAddressRange(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,COMMIT_VA_STATE const *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,bool,VIDMM_ALLOC * *)

- ea: `0x14009b008`
- end: `0x14009b524`
- name: `?CommitVirtualAddressRange@VIDMM_PAGE_TABLE@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUCOMMIT_VA_STATE@@_K333_NPEAPEAUVIDMM_ALLOC@@@Z`
- size: `1308`
- prototype: `__int64 __usercall@<rax>(VIDMM_PAGE_TABLE *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, struct CVirtualAddressAllocator *@<r8>, const struct COMMIT_VA_STATE *@<r9>, unsigned __int64, unsigned __int64, unsigned __int64, unsigned __int64, bool, struct VIDMM_ALLOC **)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140099e9c`
- `0x1400aa76c`
- `0x1400c6150`

## callees

- `0x140004268`
- `0x14002e6c0`
- `0x14002ed58`
- `0x14009aea0`
- `0x14009b008`
- `0x14009b52c`
- `0x14009c8bc`
- `0x1400ab18c`
- `0x140103950`
- `0x140113710`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x14009b09e`
- `watchdog!WdLogSingleEntry2` at `0x14009b09e`
- `watchdog!WdLogSingleEntry0` at `0x14009b12e`
- `watchdog!WdLogSingleEntry0` at `0x14009b214`
- `watchdog!WdLogSingleEntry0` at `0x14009b29a`
- `watchdog!WdLogSingleEntry0` at `0x14009b12e`
- `watchdog!WdLogSingleEntry0` at `0x14009b214`
- `watchdog!WdLogSingleEntry0` at `0x14009b29a`

## pseudocode

```c

```
