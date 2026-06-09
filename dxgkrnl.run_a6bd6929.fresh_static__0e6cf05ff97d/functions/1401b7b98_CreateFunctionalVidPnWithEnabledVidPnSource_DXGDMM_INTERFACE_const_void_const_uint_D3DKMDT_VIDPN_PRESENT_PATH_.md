# CreateFunctionalVidPnWithEnabledVidPnSource(_DXGDMM_INTERFACE const *,void * const,uint,_D3DKMDT_VIDPN_PRESENT_PATH_SCALING,uchar,_DXGK_DISPLAYMODE_INFO *,D3DKMDT_HVIDPN__ * *,_DXGDMM_VIDPN_INTERFACE const * *,uint (*)[16])

- ea: `0x1401b7b98`
- end: `0x1401b82ad`
- name: `?CreateFunctionalVidPnWithEnabledVidPnSource@@YAJPEBU_DXGDMM_INTERFACE@@QEAXIW4_D3DKMDT_VIDPN_PRESENT_PATH_SCALING@@EPEAU_DXGK_DISPLAYMODE_INFO@@PEAPEAUD3DKMDT_HVIDPN__@@PEAPEBU_DXGDMM_VIDPN_INTERFACE@@PEAY0BA@I@Z`
- size: `1813`
- prototype: `__int64 __fastcall(const struct _DXGDMM_INTERFACE *, void *const, unsigned int, enum _D3DKMDT_VIDPN_PRESENT_PATH_SCALING, unsigned __int8, struct _D3DDDI_RATIONAL *, struct D3DKMDT_HVIDPN__ **, const struct _DXGDMM_VIDPN_INTERFACE **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1401d261c`

## callees

- `0x14001b9c0`
- `0x140047b60`
- `0x1400a0cb0`
- `0x1401b7b98`
- `0x14022c4c8`
- `0x14022cf70`
- `0x140339acc`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x1401b7ea1`
- `watchdog!WdLogSingleEntry2` at `0x1401b7f3b`
- `watchdog!WdLogSingleEntry2` at `0x1401b802e`
- `watchdog!WdLogSingleEntry2` at `0x1401b8078`
- `watchdog!WdLogSingleEntry2` at `0x1401b7ea1`
- `watchdog!WdLogSingleEntry2` at `0x1401b7f3b`
- `watchdog!WdLogSingleEntry2` at `0x1401b802e`
- `watchdog!WdLogSingleEntry2` at `0x1401b8078`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401b817e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401b817e`
- `watchdog!WdLogSingleEntry3` at `0x1401b7e03`
- `watchdog!WdLogSingleEntry3` at `0x1401b80c3`
- `watchdog!WdLogSingleEntry3` at `0x1401b7e03`
- `watchdog!WdLogSingleEntry3` at `0x1401b80c3`
- `watchdog!WdLogSingleEntry0` at `0x1401b7be5`
- `watchdog!WdLogSingleEntry0` at `0x1401b7c35`
- `watchdog!WdLogSingleEntry0` at `0x1401b7c87`
- `watchdog!WdLogSingleEntry0` at `0x1401b7cd5`
- `watchdog!WdLogSingleEntry0` at `0x1401b7d24`
- `watchdog!WdLogSingleEntry0` at `0x1401b7d75`
- `watchdog!WdLogSingleEntry0` at `0x1401b7be5`
- `watchdog!WdLogSingleEntry0` at `0x1401b7c35`
- `watchdog!WdLogSingleEntry0` at `0x1401b7c87`
- `watchdog!WdLogSingleEntry0` at `0x1401b7cd5`
- `watchdog!WdLogSingleEntry0` at `0x1401b7d24`
- `watchdog!WdLogSingleEntry0` at `0x1401b7d75`
- `watchdog!WdLogSingleEntry5` at `0x1401b81ec`
- `watchdog!WdLogSingleEntry5` at `0x1401b81ec`

## string_xrefs

- `0x1401b80e1`: `Failed to ensure unpinned paths from source 0x%I64x of adapter 0x%I64x (status = 0x%I64x)`
- `0x1401b7eb2`: `Failed call to create copy of the last VidPN committed by the client for adapter 0x%I64x (status = 0x%I64x)`
- `0x1401b8202`: `Failed to pin source/target modes on VidPN present (multi)path from source 0x%I64x matching specified display mode (%I64d x %I64d x 0x%I64x @ %I64d[Hz])`

## pseudocode

```c

```
