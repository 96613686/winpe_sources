# CreateFunctionalVidPnWithEnabledVidPnSource(_DXGDMM_INTERFACE const *,void * const,uint,_D3DKMDT_VIDPN_PRESENT_PATH_SCALING,uchar,_DXGK_DISPLAYMODE_INFO *,D3DKMDT_HVIDPN__ * *,_DXGDMM_VIDPN_INTERFACE const * *,uint (*)[16])

- ea: `0x1401b4f98`
- end: `0x1401b56ad`
- name: `?CreateFunctionalVidPnWithEnabledVidPnSource@@YAJPEBU_DXGDMM_INTERFACE@@QEAXIW4_D3DKMDT_VIDPN_PRESENT_PATH_SCALING@@EPEAU_DXGK_DISPLAYMODE_INFO@@PEAPEAUD3DKMDT_HVIDPN__@@PEAPEBU_DXGDMM_VIDPN_INTERFACE@@PEAY0BA@I@Z`
- size: `1813`
- prototype: `__int64 __usercall@<rax>(const struct _DXGDMM_INTERFACE *@<rcx>, void *const@<rdx>, unsigned int@<r8d>, enum _D3DKMDT_VIDPN_PRESENT_PATH_SCALING@<r9d>, unsigned __int8, struct _DXGK_DISPLAYMODE_INFO *, struct D3DKMDT_HVIDPN__ **, const struct _DXGDMM_VIDPN_INTERFACE **, unsigned int (*)[16])`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1401cfa1c`

## callees

- `0x14001b890`
- `0x140047960`
- `0x1400a01e0`
- `0x1401b4f98`
- `0x140229e68`
- `0x14022a910`
- `0x1403330ac`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x1401b52a1`
- `watchdog!WdLogSingleEntry2` at `0x1401b533b`
- `watchdog!WdLogSingleEntry2` at `0x1401b542e`
- `watchdog!WdLogSingleEntry2` at `0x1401b5478`
- `watchdog!WdLogSingleEntry2` at `0x1401b52a1`
- `watchdog!WdLogSingleEntry2` at `0x1401b533b`
- `watchdog!WdLogSingleEntry2` at `0x1401b542e`
- `watchdog!WdLogSingleEntry2` at `0x1401b5478`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401b557e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401b557e`
- `watchdog!WdLogSingleEntry3` at `0x1401b5203`
- `watchdog!WdLogSingleEntry3` at `0x1401b54c3`
- `watchdog!WdLogSingleEntry3` at `0x1401b5203`
- `watchdog!WdLogSingleEntry3` at `0x1401b54c3`
- `watchdog!WdLogSingleEntry0` at `0x1401b4fe5`
- `watchdog!WdLogSingleEntry0` at `0x1401b5035`
- `watchdog!WdLogSingleEntry0` at `0x1401b5087`
- `watchdog!WdLogSingleEntry0` at `0x1401b50d5`
- `watchdog!WdLogSingleEntry0` at `0x1401b5124`
- `watchdog!WdLogSingleEntry0` at `0x1401b5175`
- `watchdog!WdLogSingleEntry0` at `0x1401b4fe5`
- `watchdog!WdLogSingleEntry0` at `0x1401b5035`
- `watchdog!WdLogSingleEntry0` at `0x1401b5087`
- `watchdog!WdLogSingleEntry0` at `0x1401b50d5`
- `watchdog!WdLogSingleEntry0` at `0x1401b5124`
- `watchdog!WdLogSingleEntry0` at `0x1401b5175`
- `watchdog!WdLogSingleEntry5` at `0x1401b55ec`
- `watchdog!WdLogSingleEntry5` at `0x1401b55ec`

## string_xrefs

- `0x1401b54e1`: `Failed to ensure unpinned paths from source 0x%I64x of adapter 0x%I64x (status = 0x%I64x)`
- `0x1401b52b2`: `Failed call to create copy of the last VidPN committed by the client for adapter 0x%I64x (status = 0x%I64x)`
- `0x1401b5602`: `Failed to pin source/target modes on VidPN present (multi)path from source 0x%I64x matching specified display mode (%I64d x %I64d x 0x%I64x @ %I64d[Hz])`

## pseudocode

```c

```
