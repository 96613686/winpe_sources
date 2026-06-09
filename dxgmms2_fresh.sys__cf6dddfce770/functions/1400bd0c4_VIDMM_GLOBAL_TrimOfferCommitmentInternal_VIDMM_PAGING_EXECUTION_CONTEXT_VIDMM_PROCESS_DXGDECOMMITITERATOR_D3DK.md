# VIDMM_GLOBAL::TrimOfferCommitmentInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PROCESS *,DXGDECOMMITITERATOR *,_D3DKMT_TRIMPROCESSCOMMITMENT_FLAGS,unsigned __int64,unsigned __int64 *)

- ea: `0x1400bd0c4`
- end: `0x1400bd302`
- name: `?TrimOfferCommitmentInternal@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVVIDMM_PROCESS@@PEAUDXGDECOMMITITERATOR@@T_D3DKMT_TRIMPROCESSCOMMITMENT_FLAGS@@_KPEA_K@Z`
- size: `574`
- prototype: `void __usercall(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, struct VIDMM_PROCESS *@<r8>, struct DXGDECOMMITITERATOR *@<r9>, union _D3DKMT_TRIMPROCESSCOMMITMENT_FLAGS, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400bbd5c`
- `0x140126e2c`

## callees

- `0x140012690`
- `0x14002bc54`
- `0x14002bcc0`
- `0x14002bddc`
- `0x1400b7298`
- `0x1400ba20c`
- `0x1400bd0c4`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd228`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bd228`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd234`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd234`
- `watchdog!WdLogSingleEntry3` at `0x1400bd2c9`
- `watchdog!WdLogSingleEntry3` at `0x1400bd2c9`
- `watchdog!WdLogSingleEntry1` at `0x1400bd103`
- `watchdog!WdLogSingleEntry1` at `0x1400bd103`

## pseudocode

```c

```
