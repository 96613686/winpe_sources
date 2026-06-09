# ReclaimClonedVidPnTarget(_DXGDMM_INTERFACE const *,void * const,D3DKMDT_HVIDPNTOPOLOGY__ * const,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const *,uchar,uint * const,uint * const)

- ea: `0x1401a089c`
- end: `0x1401a0f9b`
- name: `?ReclaimClonedVidPnTarget@@YAJPEBU_DXGDMM_INTERFACE@@QEAXQEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@EQEAI4@Z`
- size: `1791`
- prototype: `__int64 __fastcall(const struct _DXGDMM_INTERFACE *, void *const, struct D3DKMDT_HVIDPNTOPOLOGY__ *const, const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *, char, unsigned int *const, unsigned int *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1402294a0`

## callees

- `0x14001b890`
- `0x140047960`
- `0x1400a01e0`
- `0x1401a089c`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x1401a0e5a`
- `watchdog!WdLogSingleEntry4` at `0x1401a0e5a`
- `watchdog!WdLogSingleEntry2` at `0x1401a0ae4`
- `watchdog!WdLogSingleEntry2` at `0x1401a0b71`
- `watchdog!WdLogSingleEntry2` at `0x1401a0ae4`
- `watchdog!WdLogSingleEntry2` at `0x1401a0b71`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401a0f2a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401a0f2a`
- `watchdog!WdLogSingleEntry3` at `0x1401a0d26`
- `watchdog!WdLogSingleEntry3` at `0x1401a0da8`
- `watchdog!WdLogSingleEntry3` at `0x1401a0ebb`
- `watchdog!WdLogSingleEntry3` at `0x1401a0d26`
- `watchdog!WdLogSingleEntry3` at `0x1401a0da8`
- `watchdog!WdLogSingleEntry3` at `0x1401a0ebb`
- `watchdog!WdLogSingleEntry0` at `0x1401a08d6`
- `watchdog!WdLogSingleEntry0` at `0x1401a0924`
- `watchdog!WdLogSingleEntry0` at `0x1401a0972`
- `watchdog!WdLogSingleEntry0` at `0x1401a09c0`
- `watchdog!WdLogSingleEntry0` at `0x1401a0a14`
- `watchdog!WdLogSingleEntry0` at `0x1401a0a66`
- `watchdog!WdLogSingleEntry0` at `0x1401a0bce`
- `watchdog!WdLogSingleEntry0` at `0x1401a0c74`
- `watchdog!WdLogSingleEntry0` at `0x1401a0ddc`
- `watchdog!WdLogSingleEntry0` at `0x1401a08d6`
- `watchdog!WdLogSingleEntry0` at `0x1401a0924`
- `watchdog!WdLogSingleEntry0` at `0x1401a0972`
- `watchdog!WdLogSingleEntry0` at `0x1401a09c0`
- `watchdog!WdLogSingleEntry0` at `0x1401a0a14`
- `watchdog!WdLogSingleEntry0` at `0x1401a0a66`
- `watchdog!WdLogSingleEntry0` at `0x1401a0bce`
- `watchdog!WdLogSingleEntry0` at `0x1401a0c74`
- `watchdog!WdLogSingleEntry0` at `0x1401a0ddc`

## string_xrefs

- `0x1401a0ec7`: `Failed to get the number of paths in topology 0x%I64x originating from source 0x%I64x (status = 0x%I64x)`
- `0x1401a0db4`: `Failed to get target of the second path in topology 0x%I64x originating from source 0x%I64x (status = 0x%I64x)`
- `0x1401a0e69`: `Failed to remove path (0x%I64x, 0x%I64x) from topology 0x%I64x which is the second path originating from that source (status = 0x%I64x)`
- `0x1401a0a77`: `o_pReclaimedPathSourceId != NULL`
- `0x1401a0c85`: `sztNumPathsFromSource == 0`

## pseudocode

```c

```
