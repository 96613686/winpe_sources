# VIDMM_PAGE_DIRECTORY::ExpandZeroPte(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,COMMIT_VA_STATE const *,uint,uint,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,VIDMM_ALLOC * *)

- ea: `0x1400aa76c`
- end: `0x1400aaa49`
- name: `?ExpandZeroPte@VIDMM_PAGE_DIRECTORY@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUCOMMIT_VA_STATE@@II_K333PEAPEAUVIDMM_ALLOC@@@Z`
- size: `733`
- prototype: `__int64 __usercall@<rax>(VIDMM_PAGE_DIRECTORY *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, struct CVirtualAddressAllocator *@<r8>, const struct COMMIT_VA_STATE *@<r9>, unsigned int, unsigned int, unsigned __int64, unsigned __int64, unsigned __int64, unsigned __int64, struct VIDMM_ALLOC **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140099e9c`

## callees

- `0x140004268`
- `0x140058f50`
- `0x140059380`
- `0x140099e9c`
- `0x14009b008`
- `0x1400aa76c`
- `0x1400f1dcc`
- `0x14010bdd8`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x1400aa7ff`
- `watchdog!WdLogSingleEntry0` at `0x1400aa8ea`
- `watchdog!WdLogSingleEntry0` at `0x1400aa939`
- `watchdog!WdLogSingleEntry0` at `0x1400aa9be`
- `watchdog!WdLogSingleEntry0` at `0x1400aa9ed`
- `watchdog!WdLogSingleEntry0` at `0x1400aa7ff`
- `watchdog!WdLogSingleEntry0` at `0x1400aa8ea`
- `watchdog!WdLogSingleEntry0` at `0x1400aa939`
- `watchdog!WdLogSingleEntry0` at `0x1400aa9be`
- `watchdog!WdLogSingleEntry0` at `0x1400aa9ed`

## string_xrefs

- `0x1400aa80d`: `Failed to create page table or page directory`

## pseudocode

```c

```
