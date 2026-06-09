# UnpinCofuncModalityOnPathsFromSource(D3DKMDT_HVIDPN__ *,_DXGDMM_VIDPN_INTERFACE const *,D3DKMDT_HVIDPNTOPOLOGY__ *,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const *,uint,unsigned __int64)

- ea: `0x1401a40e8`
- end: `0x1401a491d`
- name: `?UnpinCofuncModalityOnPathsFromSource@@YAJPEAUD3DKMDT_HVIDPN__@@PEBU_DXGDMM_VIDPN_INTERFACE@@PEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@I_K@Z`
- size: `2101`
- prototype: `__int64 __fastcall(struct D3DKMDT_HVIDPN__ *, const struct _DXGDMM_VIDPN_INTERFACE *, struct D3DKMDT_HVIDPNTOPOLOGY__ *, const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x14022a910`

## callees

- `0x14001b890`
- `0x140046520`
- `0x140047960`
- `0x1400a01e0`
- `0x1401a40e8`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x1401a46c2`
- `watchdog!WdLogSingleEntry4` at `0x1401a471b`
- `watchdog!WdLogSingleEntry4` at `0x1401a4836`
- `watchdog!WdLogSingleEntry4` at `0x1401a488b`
- `watchdog!WdLogSingleEntry4` at `0x1401a46c2`
- `watchdog!WdLogSingleEntry4` at `0x1401a471b`
- `watchdog!WdLogSingleEntry4` at `0x1401a4836`
- `watchdog!WdLogSingleEntry4` at `0x1401a488b`
- `watchdog!WdLogSingleEntry2` at `0x1401a4416`
- `watchdog!WdLogSingleEntry2` at `0x1401a4416`
- `watchdog!WdLogSingleEntry3` at `0x1401a42e9`
- `watchdog!WdLogSingleEntry3` at `0x1401a42e9`
- `watchdog!WdLogSingleEntry0` at `0x1401a4123`
- `watchdog!WdLogSingleEntry0` at `0x1401a4170`
- `watchdog!WdLogSingleEntry0` at `0x1401a41bd`
- `watchdog!WdLogSingleEntry0` at `0x1401a420a`
- `watchdog!WdLogSingleEntry0` at `0x1401a425c`
- `watchdog!WdLogSingleEntry0` at `0x1401a4341`
- `watchdog!WdLogSingleEntry0` at `0x1401a4393`
- `watchdog!WdLogSingleEntry0` at `0x1401a44c3`
- `watchdog!WdLogSingleEntry0` at `0x1401a4579`
- `watchdog!WdLogSingleEntry0` at `0x1401a45cb`
- `watchdog!WdLogSingleEntry0` at `0x1401a4123`
- `watchdog!WdLogSingleEntry0` at `0x1401a4170`
- `watchdog!WdLogSingleEntry0` at `0x1401a41bd`
- `watchdog!WdLogSingleEntry0` at `0x1401a420a`
- `watchdog!WdLogSingleEntry0` at `0x1401a425c`
- `watchdog!WdLogSingleEntry0` at `0x1401a4341`
- `watchdog!WdLogSingleEntry0` at `0x1401a4393`
- `watchdog!WdLogSingleEntry0` at `0x1401a44c3`
- `watchdog!WdLogSingleEntry0` at `0x1401a4579`
- `watchdog!WdLogSingleEntry0` at `0x1401a45cb`
- `watchdog!WdLogSingleEntry1` at `0x1401a4765`
- `watchdog!WdLogSingleEntry1` at `0x1401a47ce`
- `watchdog!WdLogSingleEntry1` at `0x1401a4765`
- `watchdog!WdLogSingleEntry1` at `0x1401a47ce`

## string_xrefs

- `0x1401a472a`: `Failed to unpin scaling on present path (0x%I64x, 0x%I64x) in topology 0x%I64x (status = 0x%I64x)`
- `0x1401a4782`: `cdd!AcquirePresentPathUnpinnedCofuncModality failed call to DXGDMM_VIDPNTARGETMODESET_INTERFACE::pfnUnpinMode. (status = 0x%I64x)`
- `0x1401a4845`: `Failed to remove copy protection on present path (0x%I64x, 0x%I64x) in topology 0x%I64x (status = 0x%I64x)`
- `0x1401a47eb`: `cdd!AcquirePresentPathUnpinnedCofuncModality failed call to DXGDMM_VIDPN_INTERFACE::pfnAcquireTargetModeSet. (status = 0x%I64x)`
- `0x1401a46d1`: `Failed to unpin rotation on present path (0x%I64x, 0x%I64x) in topology 0x%I64x (status = 0x%I64x)`
- `0x1401a48a0`: `Failed to enumerate target of %I64d'th path originating from source 0x%I64x in VidPN topology 0x%I64x (status = 0x%I64x)`

## pseudocode

```c

```
