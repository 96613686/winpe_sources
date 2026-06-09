# DXGCONTEXT::SubmitPresent(_D3DKMT_PRESENT const *,DXGHWQUEUE * *,uint,DXGCONTEXT * *,DXGALLOCATION *,uint,uint,_DXGKARG_PRESENT *,_D3DKMT_PRESENT_RGNS *,VIDMM_DMA_BUFFER *,VIDSCH_SUBMIT_DATA_BASE *,_D3DDDIFORMAT,COREDEVICEACCESS *)

- ea: `0x14031a9cc`
- end: `0x14031bf29`
- name: `?SubmitPresent@DXGCONTEXT@@QEAAJPEBU_D3DKMT_PRESENT@@PEAPEAVDXGHWQUEUE@@IPEAPEAV1@PEAVDXGALLOCATION@@IIPEAU_DXGKARG_PRESENT@@PEAU_D3DKMT_PRESENT_RGNS@@PEAUVIDMM_DMA_BUFFER@@PEAUVIDSCH_SUBMIT_DATA_BASE@@W4_D3DDDIFORMAT@@PEAVCOREDEVICEACCESS@@@Z`
- size: `5469`
- prototype: `__int64 __fastcall(DXGCONTEXT *this, struct _D3DKMT_PRESENT *, struct DXGHWQUEUE **, unsigned int, struct DXGCONTEXT **, struct DXGALLOCATION *, unsigned int, unsigned int, struct _DXGKARG_PRESENT *, struct _D3DKMT_PRESENT_RGNS *, struct VIDMM_DMA_BUFFER *, struct VIDSCH_SUBMIT_DATA_BASE *, enum _D3DDDIFORMAT, struct COREDEVICEACCESS *)`
- caller_count: `4`
- callee_count: `29`
- tags: `service_task`

## callers

- `0x140251ea8`
- `0x140254210`
- `0x1403930a8`
- `0x14039aac0`

## callees

- `0x14001b9c0`
- `0x14001c450`
- `0x14002dbc0`
- `0x14002e330`
- `0x14002e3b0`
- `0x14002ff90`
- `0x140037ef0`
- `0x14003cd10`
- `0x14003feb4`
- `0x140046d28`
- `0x1400477c4`
- `0x14004d4a4`
- `0x1400674c4`
- `0x140075f74`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x140194bbc`
- `0x140255918`
- `0x140319abc`
- `0x14031a444`
- `0x14031a9cc`
- `0x14031bf30`
- `0x14032e980`
- `0x14033464c`
- `0x14037ecf0`
- `0x1403bed48`
- `0x1403cfdc0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14031b2a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031b462`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031b2a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031b462`
- `ntoskrnl!ExAllocatePool2` at `0x14031b308`
- `ntoskrnl!ExAllocatePool2` at `0x14031b308`
- `watchdog!WdLogSingleEntry2` at `0x14031b694`
- `watchdog!WdLogSingleEntry2` at `0x14031b6cd`
- `watchdog!WdLogSingleEntry2` at `0x14031ba6c`
- `watchdog!WdLogSingleEntry2` at `0x14031bb48`
- `watchdog!WdLogSingleEntry2` at `0x14031b694`
- `watchdog!WdLogSingleEntry2` at `0x14031b6cd`
- `watchdog!WdLogSingleEntry2` at `0x14031ba6c`
- `watchdog!WdLogSingleEntry2` at `0x14031bb48`
- `watchdog!WdLogSingleEntry3` at `0x14031b8e7`
- `watchdog!WdLogSingleEntry3` at `0x14031b994`
- `watchdog!WdLogSingleEntry3` at `0x14031b8e7`
- `watchdog!WdLogSingleEntry3` at `0x14031b994`
- `watchdog!WdLogSingleEntry0` at `0x14031b114`
- `watchdog!WdLogSingleEntry0` at `0x14031b47c`
- `watchdog!WdLogSingleEntry0` at `0x14031bd66`
- `watchdog!WdLogSingleEntry0` at `0x14031bdb5`
- `watchdog!WdLogSingleEntry0` at `0x14031b114`
- `watchdog!WdLogSingleEntry0` at `0x14031b47c`
- `watchdog!WdLogSingleEntry0` at `0x14031bd66`
- `watchdog!WdLogSingleEntry0` at `0x14031bdb5`
- `watchdog!WdLogSingleEntry1` at `0x14031b3ed`
- `watchdog!WdLogSingleEntry1` at `0x14031b573`
- `watchdog!WdLogSingleEntry1` at `0x14031b714`
- `watchdog!WdLogSingleEntry1` at `0x14031b808`
- `watchdog!WdLogSingleEntry1` at `0x14031bbb7`
- `watchdog!WdLogSingleEntry1` at `0x14031b3ed`
- `watchdog!WdLogSingleEntry1` at `0x14031b573`
- `watchdog!WdLogSingleEntry1` at `0x14031b714`
- `watchdog!WdLogSingleEntry1` at `0x14031b808`
- `watchdog!WdLogSingleEntry1` at `0x14031bbb7`

## string_xrefs

- `0x14031b420`: `DXGCONTEXT 0x%p broadcast present mixes hardware scheduled and non-hardware scheduled contexts.`
- `0x14031b5a2`: `Failed to read private driver data. Returning 0x%I64x`
- `0x14031b837`: `Failed to create present sync object. Returning 0x%I64x`
- `0x14031bbfa`: `Encountered exception reading allocation handles. Returning 0x%I64x`

## pseudocode

```c

```
