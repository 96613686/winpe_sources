# DXGCONTEXT::SubmitPresentMultiPlaneOverlays3(_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 const *,uchar,uchar,uchar,DXGALLOCATIONREFERENCE const *,uchar *,_DXGKARG_PRESENT *,VIDSCH_SUBMIT_DATA_BASE *,DXGCONTEXT * *)

- ea: `0x140318248`
- end: `0x14031997c`
- name: `?SubmitPresentMultiPlaneOverlays3@DXGCONTEXT@@AEAAJPEBU_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@EEEPEBVDXGALLOCATIONREFERENCE@@PEAEPEAU_DXGKARG_PRESENT@@PEAUVIDSCH_SUBMIT_DATA_BASE@@PEAPEAV1@@Z`
- size: `5940`
- prototype: `__int64 __usercall@<rax>(DXGCONTEXT *__hidden this@<rcx>, const struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, char, const struct DXGALLOCATIONREFERENCE *, unsigned __int8 *, struct _DXGKARG_PRESENT *, struct VIDSCH_SUBMIT_DATA_BASE *, struct DXGCONTEXT **)`
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x1404098b8`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x14002dbc0`
- `0x14002e3b0`
- `0x14002ff90`
- `0x140030a30`
- `0x140033da4`
- `0x140037870`
- `0x14003cd10`
- `0x140047990`
- `0x140049364`
- `0x140075f74`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x140318248`
- `0x140319984`
- `0x140319a04`
- `0x140319abc`
- `0x140319dd8`
- `0x14031a444`
- `0x14031a4a8`
- `0x14031a6b4`
- `0x14031a824`
- `0x14033464c`
- `0x14037e684`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1403185b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140318fde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031908d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403198e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403198f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403185b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140318fde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031908d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403198e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403198f6`
- `watchdog!WdLogSingleEntry4` at `0x14031925a`
- `watchdog!WdLogSingleEntry4` at `0x14031925a`
- `watchdog!WdLogSingleEntry2` at `0x140319135`
- `watchdog!WdLogSingleEntry2` at `0x1403192a7`
- `watchdog!WdLogSingleEntry2` at `0x140319135`
- `watchdog!WdLogSingleEntry2` at `0x1403192a7`
- `watchdog!WdLogSingleEntry3` at `0x14031980a`
- `watchdog!WdLogSingleEntry3` at `0x14031980a`
- `watchdog!WdLogSingleEntry0` at `0x14031896a`
- `watchdog!WdLogSingleEntry0` at `0x140318cdb`
- `watchdog!WdLogSingleEntry0` at `0x14031919f`
- `watchdog!WdLogSingleEntry0` at `0x1403191f2`
- `watchdog!WdLogSingleEntry0` at `0x140319356`
- `watchdog!WdLogSingleEntry0` at `0x1403193a7`
- `watchdog!WdLogSingleEntry0` at `0x1403193f8`
- `watchdog!WdLogSingleEntry0` at `0x140319496`
- `watchdog!WdLogSingleEntry0` at `0x1403194ed`
- `watchdog!WdLogSingleEntry0` at `0x140319584`
- `watchdog!WdLogSingleEntry0` at `0x140319633`
- `watchdog!WdLogSingleEntry0` at `0x14031968b`
- `watchdog!WdLogSingleEntry0` at `0x1403196f3`
- `watchdog!WdLogSingleEntry0` at `0x140319862`
- `watchdog!WdLogSingleEntry0` at `0x14031896a`
- `watchdog!WdLogSingleEntry0` at `0x140318cdb`
- `watchdog!WdLogSingleEntry0` at `0x14031919f`
- `watchdog!WdLogSingleEntry0` at `0x1403191f2`
- `watchdog!WdLogSingleEntry0` at `0x140319356`
- `watchdog!WdLogSingleEntry0` at `0x1403193a7`
- `watchdog!WdLogSingleEntry0` at `0x1403193f8`
- `watchdog!WdLogSingleEntry0` at `0x140319496`
- `watchdog!WdLogSingleEntry0` at `0x1403194ed`
- `watchdog!WdLogSingleEntry0` at `0x140319584`
- `watchdog!WdLogSingleEntry0` at `0x140319633`
- `watchdog!WdLogSingleEntry0` at `0x14031968b`
- `watchdog!WdLogSingleEntry0` at `0x1403196f3`
- `watchdog!WdLogSingleEntry0` at `0x140319862`
- `watchdog!WdLogSingleEntry1` at `0x140318f18`
- `watchdog!WdLogSingleEntry1` at `0x140319006`
- `watchdog!WdLogSingleEntry1` at `0x1403192e9`
- `watchdog!WdLogSingleEntry1` at `0x1403197a1`
- `watchdog!WdLogSingleEntry1` at `0x140318f18`
- `watchdog!WdLogSingleEntry1` at `0x140319006`
- `watchdog!WdLogSingleEntry1` at `0x1403192e9`
- `watchdog!WdLogSingleEntry1` at `0x1403197a1`

## string_xrefs

- `0x1403192fa`: `Failed to read dirty rects data. Returning 0x%I64x`
- `0x1403197b6`: `Failed to read private driver data. Returning 0x%I64x`

## pseudocode

```c

```
