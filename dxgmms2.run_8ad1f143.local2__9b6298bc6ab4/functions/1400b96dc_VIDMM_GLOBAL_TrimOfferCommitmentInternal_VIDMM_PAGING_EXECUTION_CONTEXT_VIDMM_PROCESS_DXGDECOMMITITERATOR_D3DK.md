# VIDMM_GLOBAL::TrimOfferCommitmentInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PROCESS *,DXGDECOMMITITERATOR *,_D3DKMT_TRIMPROCESSCOMMITMENT_FLAGS,unsigned __int64,unsigned __int64 *)

- ea: `0x1400b96dc`
- end: `0x1400b991a`
- name: `?TrimOfferCommitmentInternal@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVVIDMM_PROCESS@@PEAUDXGDECOMMITITERATOR@@T_D3DKMT_TRIMPROCESSCOMMITMENT_FLAGS@@_KPEA_K@Z`
- size: `574`
- prototype: `void __usercall(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, struct VIDMM_PROCESS *@<r8>, struct DXGDECOMMITITERATOR *@<r9>, union _D3DKMT_TRIMPROCESSCOMMITMENT_FLAGS, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400b8374`
- `0x1400e8d90`

## callees

- `0x140012bf0`
- `0x14002eb94`
- `0x14002ec00`
- `0x14002ed1c`
- `0x1400b395c`
- `0x1400b6834`
- `0x1400b96dc`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b9840`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b9840`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b984c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b984c`
- `watchdog!WdLogSingleEntry3` at `0x1400b98e1`
- `watchdog!WdLogSingleEntry3` at `0x1400b98e1`
- `watchdog!WdLogSingleEntry1` at `0x1400b971b`
- `watchdog!WdLogSingleEntry1` at `0x1400b971b`

## pseudocode

```c

```
