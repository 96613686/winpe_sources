# AugmentVidPnTopologyOnNoLkg(D3DKMDT_HVIDPNTOPOLOGY__ *,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const *,void *,_DXGDMM_INTERFACE const *,uint,_D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE,ushort,uchar,unsigned __int64 * const,uint * const)

- ea: `0x14022bb00`
- end: `0x14022c0dd`
- name: `?AugmentVidPnTopologyOnNoLkg@@YAJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@PEAXPEBU_DXGDMM_INTERFACE@@IW4_D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE@@GEQEA_KQEAI@Z`
- size: `1501`
- prototype: `__int64 __usercall@<rax>(struct D3DKMDT_HVIDPNTOPOLOGY__ *@<rcx>, const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *@<rdx>, void *@<r8>, const struct _DXGDMM_INTERFACE *@<r9>, unsigned int, enum _D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE, unsigned __int16, unsigned __int8, unsigned __int64 *const, unsigned int *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x14022b678`

## callees

- `0x14001b9c0`
- `0x1401a4b5c`
- `0x14022b368`
- `0x14022b540`
- `0x14022bb00`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x14022bfb1`
- `watchdog!WdLogSingleEntry4` at `0x14022bfb1`
- `watchdog!WdLogSingleEntry2` at `0x14022bd68`
- `watchdog!WdLogSingleEntry2` at `0x14022bdb4`
- `watchdog!WdLogSingleEntry2` at `0x14022bd68`
- `watchdog!WdLogSingleEntry2` at `0x14022bdb4`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14022be1d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14022be1d`
- `watchdog!WdLogSingleEntry3` at `0x14022be57`
- `watchdog!WdLogSingleEntry3` at `0x14022beff`
- `watchdog!WdLogSingleEntry3` at `0x14022bf4a`
- `watchdog!WdLogSingleEntry3` at `0x14022bf7c`
- `watchdog!WdLogSingleEntry3` at `0x14022c042`
- `watchdog!WdLogSingleEntry3` at `0x14022c088`
- `watchdog!WdLogSingleEntry3` at `0x14022be57`
- `watchdog!WdLogSingleEntry3` at `0x14022beff`
- `watchdog!WdLogSingleEntry3` at `0x14022bf4a`
- `watchdog!WdLogSingleEntry3` at `0x14022bf7c`
- `watchdog!WdLogSingleEntry3` at `0x14022c042`
- `watchdog!WdLogSingleEntry3` at `0x14022c088`
- `watchdog!WdLogSingleEntry0` at `0x14022bb44`
- `watchdog!WdLogSingleEntry0` at `0x14022bb90`
- `watchdog!WdLogSingleEntry0` at `0x14022bbdc`
- `watchdog!WdLogSingleEntry0` at `0x14022bc28`
- `watchdog!WdLogSingleEntry0` at `0x14022bc7c`
- `watchdog!WdLogSingleEntry0` at `0x14022bcd4`
- `watchdog!WdLogSingleEntry0` at `0x14022bea3`
- `watchdog!WdLogSingleEntry0` at `0x14022bb44`
- `watchdog!WdLogSingleEntry0` at `0x14022bb90`
- `watchdog!WdLogSingleEntry0` at `0x14022bbdc`
- `watchdog!WdLogSingleEntry0` at `0x14022bc28`
- `watchdog!WdLogSingleEntry0` at `0x14022bc7c`
- `watchdog!WdLogSingleEntry0` at `0x14022bcd4`
- `watchdog!WdLogSingleEntry0` at `0x14022bea3`

## string_xrefs

- `0x14022bfc6`: `Failed to add present path (0x%I64x, 0x%I64x) to VidPN topology 0x%I64x (status = 0x%I64x)`
- `0x14022bce5`: `ARGUMENT_PRESENT(o_pNumVidPnPresentPathsFromSource)`

## pseudocode

```c

```
