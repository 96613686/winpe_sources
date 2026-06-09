# DXGCONTEXT::SubmitPresent(_D3DKMT_PRESENT const *,DXGHWQUEUE * *,uint,DXGCONTEXT * *,DXGALLOCATION *,uint,uint,_DXGKARG_PRESENT *,_D3DKMT_PRESENT_RGNS *,VIDMM_DMA_BUFFER *,VIDSCH_SUBMIT_DATA_BASE *,_D3DDDIFORMAT,COREDEVICEACCESS *)

- ea: `0x140313c5c`
- end: `0x1403151b9`
- name: `?SubmitPresent@DXGCONTEXT@@QEAAJPEBU_D3DKMT_PRESENT@@PEAPEAVDXGHWQUEUE@@IPEAPEAV1@PEAVDXGALLOCATION@@IIPEAU_DXGKARG_PRESENT@@PEAU_D3DKMT_PRESENT_RGNS@@PEAUVIDMM_DMA_BUFFER@@PEAUVIDSCH_SUBMIT_DATA_BASE@@W4_D3DDDIFORMAT@@PEAVCOREDEVICEACCESS@@@Z`
- size: `5469`
- prototype: `int(DXGCONTEXT *__hidden this, const struct _D3DKMT_PRESENT *, struct DXGHWQUEUE **, unsigned int, struct DXGCONTEXT **, struct DXGALLOCATION *, unsigned int, unsigned int, struct _DXGKARG_PRESENT *, struct _D3DKMT_PRESENT_RGNS *, struct VIDMM_DMA_BUFFER *, struct VIDSCH_SUBMIT_DATA_BASE *, enum _D3DDDIFORMAT, struct COREDEVICEACCESS *)`
- caller_count: `4`
- callee_count: `29`
- tags: `service_task`

## callers

- `0x14024e8c8`
- `0x140250c30`
- `0x140341898`
- `0x140399ce0`

## callees

- `0x14001b890`
- `0x14001c320`
- `0x14002d9f0`
- `0x14002e160`
- `0x14002e1e0`
- `0x14002fdc0`
- `0x140037d20`
- `0x14003cab0`
- `0x14003fc54`
- `0x140046ac8`
- `0x1400475cc`
- `0x14004d2a4`
- `0x1400670a4`
- `0x1400758d4`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0240`
- `0x1400a0540`
- `0x140190bbc`
- `0x1402521e4`
- `0x140312d4c`
- `0x1403136d4`
- `0x140313c5c`
- `0x1403151c0`
- `0x140327c10`
- `0x14032d8dc`
- `0x140340d50`
- `0x1403bfa28`
- `0x1403cf9a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140314536`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403146f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140314536`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403146f2`
- `ntoskrnl!ExAllocatePool2` at `0x140314598`
- `ntoskrnl!ExAllocatePool2` at `0x140314598`
- `watchdog!WdLogSingleEntry2` at `0x140314924`
- `watchdog!WdLogSingleEntry2` at `0x14031495d`
- `watchdog!WdLogSingleEntry2` at `0x140314cfc`
- `watchdog!WdLogSingleEntry2` at `0x140314dd8`
- `watchdog!WdLogSingleEntry2` at `0x140314924`
- `watchdog!WdLogSingleEntry2` at `0x14031495d`
- `watchdog!WdLogSingleEntry2` at `0x140314cfc`
- `watchdog!WdLogSingleEntry2` at `0x140314dd8`
- `watchdog!WdLogSingleEntry3` at `0x140314b77`
- `watchdog!WdLogSingleEntry3` at `0x140314c24`
- `watchdog!WdLogSingleEntry3` at `0x140314b77`
- `watchdog!WdLogSingleEntry3` at `0x140314c24`
- `watchdog!WdLogSingleEntry0` at `0x1403143a4`
- `watchdog!WdLogSingleEntry0` at `0x14031470c`
- `watchdog!WdLogSingleEntry0` at `0x140314ff6`
- `watchdog!WdLogSingleEntry0` at `0x140315045`
- `watchdog!WdLogSingleEntry0` at `0x1403143a4`
- `watchdog!WdLogSingleEntry0` at `0x14031470c`
- `watchdog!WdLogSingleEntry0` at `0x140314ff6`
- `watchdog!WdLogSingleEntry0` at `0x140315045`
- `watchdog!WdLogSingleEntry1` at `0x14031467d`
- `watchdog!WdLogSingleEntry1` at `0x140314803`
- `watchdog!WdLogSingleEntry1` at `0x1403149a4`
- `watchdog!WdLogSingleEntry1` at `0x140314a98`
- `watchdog!WdLogSingleEntry1` at `0x140314e47`
- `watchdog!WdLogSingleEntry1` at `0x14031467d`
- `watchdog!WdLogSingleEntry1` at `0x140314803`
- `watchdog!WdLogSingleEntry1` at `0x1403149a4`
- `watchdog!WdLogSingleEntry1` at `0x140314a98`
- `watchdog!WdLogSingleEntry1` at `0x140314e47`

## string_xrefs

- `0x1403146b0`: `DXGCONTEXT 0x%p broadcast present mixes hardware scheduled and non-hardware scheduled contexts.`
- `0x140314832`: `Failed to read private driver data. Returning 0x%I64x`
- `0x140314ac7`: `Failed to create present sync object. Returning 0x%I64x`
- `0x140314e8a`: `Encountered exception reading allocation handles. Returning 0x%I64x`

## pseudocode

```c

```
