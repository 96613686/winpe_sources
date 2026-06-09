# DXGCONTEXT::SubmitPresentMultiPlaneOverlays3(_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 const *,uchar,uchar,uchar,DXGALLOCATIONREFERENCE const *,uchar *,_DXGKARG_PRESENT *,VIDSCH_SUBMIT_DATA_BASE *,DXGCONTEXT * *)

- ea: `0x1403114d8`
- end: `0x140312c0c`
- name: `?SubmitPresentMultiPlaneOverlays3@DXGCONTEXT@@AEAAJPEBU_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@EEEPEBVDXGALLOCATIONREFERENCE@@PEAEPEAU_DXGKARG_PRESENT@@PEAUVIDSCH_SUBMIT_DATA_BASE@@PEAPEAV1@@Z`
- size: `5940`
- prototype: `__int64 __usercall@<rax>(DXGCONTEXT *__hidden this@<rcx>, const struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, char, const struct DXGALLOCATIONREFERENCE *, unsigned __int8 *, struct _DXGKARG_PRESENT *, struct VIDSCH_SUBMIT_DATA_BASE *, struct DXGCONTEXT **)`
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x14033de10`

## callees

- `0x140012380`
- `0x14001b890`
- `0x14002d9f0`
- `0x14002e1e0`
- `0x14002fdc0`
- `0x140030860`
- `0x140033bd4`
- `0x1400376a0`
- `0x14003cab0`
- `0x140047790`
- `0x140049164`
- `0x1400758d4`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x1403114d8`
- `0x140312c14`
- `0x140312c94`
- `0x140312d4c`
- `0x140313068`
- `0x1403136d4`
- `0x140313738`
- `0x140313944`
- `0x140313ab4`
- `0x14032d8dc`
- `0x14038c518`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140311847`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031226e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031231d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140312b73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140312b86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140311847`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031226e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14031231d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140312b73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140312b86`
- `watchdog!WdLogSingleEntry4` at `0x1403124ea`
- `watchdog!WdLogSingleEntry4` at `0x1403124ea`
- `watchdog!WdLogSingleEntry2` at `0x1403123c5`
- `watchdog!WdLogSingleEntry2` at `0x140312537`
- `watchdog!WdLogSingleEntry2` at `0x1403123c5`
- `watchdog!WdLogSingleEntry2` at `0x140312537`
- `watchdog!WdLogSingleEntry3` at `0x140312a9a`
- `watchdog!WdLogSingleEntry3` at `0x140312a9a`
- `watchdog!WdLogSingleEntry0` at `0x140311bfa`
- `watchdog!WdLogSingleEntry0` at `0x140311f6b`
- `watchdog!WdLogSingleEntry0` at `0x14031242f`
- `watchdog!WdLogSingleEntry0` at `0x140312482`
- `watchdog!WdLogSingleEntry0` at `0x1403125e6`
- `watchdog!WdLogSingleEntry0` at `0x140312637`
- `watchdog!WdLogSingleEntry0` at `0x140312688`
- `watchdog!WdLogSingleEntry0` at `0x140312726`
- `watchdog!WdLogSingleEntry0` at `0x14031277d`
- `watchdog!WdLogSingleEntry0` at `0x140312814`
- `watchdog!WdLogSingleEntry0` at `0x1403128c3`
- `watchdog!WdLogSingleEntry0` at `0x14031291b`
- `watchdog!WdLogSingleEntry0` at `0x140312983`
- `watchdog!WdLogSingleEntry0` at `0x140312af2`
- `watchdog!WdLogSingleEntry0` at `0x140311bfa`
- `watchdog!WdLogSingleEntry0` at `0x140311f6b`
- `watchdog!WdLogSingleEntry0` at `0x14031242f`
- `watchdog!WdLogSingleEntry0` at `0x140312482`
- `watchdog!WdLogSingleEntry0` at `0x1403125e6`
- `watchdog!WdLogSingleEntry0` at `0x140312637`
- `watchdog!WdLogSingleEntry0` at `0x140312688`
- `watchdog!WdLogSingleEntry0` at `0x140312726`
- `watchdog!WdLogSingleEntry0` at `0x14031277d`
- `watchdog!WdLogSingleEntry0` at `0x140312814`
- `watchdog!WdLogSingleEntry0` at `0x1403128c3`
- `watchdog!WdLogSingleEntry0` at `0x14031291b`
- `watchdog!WdLogSingleEntry0` at `0x140312983`
- `watchdog!WdLogSingleEntry0` at `0x140312af2`
- `watchdog!WdLogSingleEntry1` at `0x1403121a8`
- `watchdog!WdLogSingleEntry1` at `0x140312296`
- `watchdog!WdLogSingleEntry1` at `0x140312579`
- `watchdog!WdLogSingleEntry1` at `0x140312a31`
- `watchdog!WdLogSingleEntry1` at `0x1403121a8`
- `watchdog!WdLogSingleEntry1` at `0x140312296`
- `watchdog!WdLogSingleEntry1` at `0x140312579`
- `watchdog!WdLogSingleEntry1` at `0x140312a31`

## string_xrefs

- `0x14031258a`: `Failed to read dirty rects data. Returning 0x%I64x`
- `0x140312a46`: `Failed to read private driver data. Returning 0x%I64x`

## pseudocode

```c

```
