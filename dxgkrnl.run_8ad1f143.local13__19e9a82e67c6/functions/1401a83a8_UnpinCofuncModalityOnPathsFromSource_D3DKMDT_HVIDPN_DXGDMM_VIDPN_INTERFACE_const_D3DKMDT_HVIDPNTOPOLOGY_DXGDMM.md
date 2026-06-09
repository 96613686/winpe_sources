# UnpinCofuncModalityOnPathsFromSource(D3DKMDT_HVIDPN__ *,_DXGDMM_VIDPN_INTERFACE const *,D3DKMDT_HVIDPNTOPOLOGY__ *,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const *,uint,unsigned __int64)

- ea: `0x1401a83a8`
- end: `0x1401a8bdd`
- name: `?UnpinCofuncModalityOnPathsFromSource@@YAJPEAUD3DKMDT_HVIDPN__@@PEBU_DXGDMM_VIDPN_INTERFACE@@PEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@I_K@Z`
- size: `2101`
- prototype: `__int64 __fastcall(struct D3DKMDT_HVIDPN__ *, const struct _DXGDMM_VIDPN_INTERFACE *, struct D3DKMDT_HVIDPNTOPOLOGY__ *, const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x14022cf70`

## callees

- `0x14001b9c0`
- `0x140046780`
- `0x140047b60`
- `0x1400a0cb0`
- `0x1401a83a8`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x1401a8982`
- `watchdog!WdLogSingleEntry4` at `0x1401a89db`
- `watchdog!WdLogSingleEntry4` at `0x1401a8af6`
- `watchdog!WdLogSingleEntry4` at `0x1401a8b4b`
- `watchdog!WdLogSingleEntry4` at `0x1401a8982`
- `watchdog!WdLogSingleEntry4` at `0x1401a89db`
- `watchdog!WdLogSingleEntry4` at `0x1401a8af6`
- `watchdog!WdLogSingleEntry4` at `0x1401a8b4b`
- `watchdog!WdLogSingleEntry2` at `0x1401a86d6`
- `watchdog!WdLogSingleEntry2` at `0x1401a86d6`
- `watchdog!WdLogSingleEntry3` at `0x1401a85a9`
- `watchdog!WdLogSingleEntry3` at `0x1401a85a9`
- `watchdog!WdLogSingleEntry0` at `0x1401a83e3`
- `watchdog!WdLogSingleEntry0` at `0x1401a8430`
- `watchdog!WdLogSingleEntry0` at `0x1401a847d`
- `watchdog!WdLogSingleEntry0` at `0x1401a84ca`
- `watchdog!WdLogSingleEntry0` at `0x1401a851c`
- `watchdog!WdLogSingleEntry0` at `0x1401a8601`
- `watchdog!WdLogSingleEntry0` at `0x1401a8653`
- `watchdog!WdLogSingleEntry0` at `0x1401a8783`
- `watchdog!WdLogSingleEntry0` at `0x1401a8839`
- `watchdog!WdLogSingleEntry0` at `0x1401a888b`
- `watchdog!WdLogSingleEntry0` at `0x1401a83e3`
- `watchdog!WdLogSingleEntry0` at `0x1401a8430`
- `watchdog!WdLogSingleEntry0` at `0x1401a847d`
- `watchdog!WdLogSingleEntry0` at `0x1401a84ca`
- `watchdog!WdLogSingleEntry0` at `0x1401a851c`
- `watchdog!WdLogSingleEntry0` at `0x1401a8601`
- `watchdog!WdLogSingleEntry0` at `0x1401a8653`
- `watchdog!WdLogSingleEntry0` at `0x1401a8783`
- `watchdog!WdLogSingleEntry0` at `0x1401a8839`
- `watchdog!WdLogSingleEntry0` at `0x1401a888b`
- `watchdog!WdLogSingleEntry1` at `0x1401a8a25`
- `watchdog!WdLogSingleEntry1` at `0x1401a8a8e`
- `watchdog!WdLogSingleEntry1` at `0x1401a8a25`
- `watchdog!WdLogSingleEntry1` at `0x1401a8a8e`

## string_xrefs

- `0x1401a89ea`: `Failed to unpin scaling on present path (0x%I64x, 0x%I64x) in topology 0x%I64x (status = 0x%I64x)`
- `0x1401a8a42`: `cdd!AcquirePresentPathUnpinnedCofuncModality failed call to DXGDMM_VIDPNTARGETMODESET_INTERFACE::pfnUnpinMode. (status = 0x%I64x)`
- `0x1401a8b05`: `Failed to remove copy protection on present path (0x%I64x, 0x%I64x) in topology 0x%I64x (status = 0x%I64x)`
- `0x1401a8aab`: `cdd!AcquirePresentPathUnpinnedCofuncModality failed call to DXGDMM_VIDPN_INTERFACE::pfnAcquireTargetModeSet. (status = 0x%I64x)`
- `0x1401a8991`: `Failed to unpin rotation on present path (0x%I64x, 0x%I64x) in topology 0x%I64x (status = 0x%I64x)`
- `0x1401a8b60`: `Failed to enumerate target of %I64d'th path originating from source 0x%I64x in VidPN topology 0x%I64x (status = 0x%I64x)`

## pseudocode

```c

```
