# AugmentVidPnTopologyOnNoLkg(D3DKMDT_HVIDPNTOPOLOGY__ *,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const *,void *,_DXGDMM_INTERFACE const *,uint,_D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE,ushort,uchar,unsigned __int64 * const,uint * const)

- ea: `0x1402294a0`
- end: `0x140229a7d`
- name: `?AugmentVidPnTopologyOnNoLkg@@YAJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@PEAXPEBU_DXGDMM_INTERFACE@@IW4_D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE@@GEQEA_KQEAI@Z`
- size: `1501`
- prototype: `__int64 __usercall@<rax>(struct D3DKMDT_HVIDPNTOPOLOGY__ *@<rcx>, const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *@<rdx>, void *@<r8>, const struct _DXGDMM_INTERFACE *@<r9>, unsigned int, enum _D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE, unsigned __int16, unsigned __int8, unsigned __int64 *const, unsigned int *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x140229018`

## callees

- `0x14001b890`
- `0x1401a089c`
- `0x140228d08`
- `0x140228ee0`
- `0x1402294a0`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x140229951`
- `watchdog!WdLogSingleEntry4` at `0x140229951`
- `watchdog!WdLogSingleEntry2` at `0x140229708`
- `watchdog!WdLogSingleEntry2` at `0x140229754`
- `watchdog!WdLogSingleEntry2` at `0x140229708`
- `watchdog!WdLogSingleEntry2` at `0x140229754`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402297bd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402297bd`
- `watchdog!WdLogSingleEntry3` at `0x1402297f7`
- `watchdog!WdLogSingleEntry3` at `0x14022989f`
- `watchdog!WdLogSingleEntry3` at `0x1402298ea`
- `watchdog!WdLogSingleEntry3` at `0x14022991c`
- `watchdog!WdLogSingleEntry3` at `0x1402299e2`
- `watchdog!WdLogSingleEntry3` at `0x140229a28`
- `watchdog!WdLogSingleEntry3` at `0x1402297f7`
- `watchdog!WdLogSingleEntry3` at `0x14022989f`
- `watchdog!WdLogSingleEntry3` at `0x1402298ea`
- `watchdog!WdLogSingleEntry3` at `0x14022991c`
- `watchdog!WdLogSingleEntry3` at `0x1402299e2`
- `watchdog!WdLogSingleEntry3` at `0x140229a28`
- `watchdog!WdLogSingleEntry0` at `0x1402294e4`
- `watchdog!WdLogSingleEntry0` at `0x140229530`
- `watchdog!WdLogSingleEntry0` at `0x14022957c`
- `watchdog!WdLogSingleEntry0` at `0x1402295c8`
- `watchdog!WdLogSingleEntry0` at `0x14022961c`
- `watchdog!WdLogSingleEntry0` at `0x140229674`
- `watchdog!WdLogSingleEntry0` at `0x140229843`
- `watchdog!WdLogSingleEntry0` at `0x1402294e4`
- `watchdog!WdLogSingleEntry0` at `0x140229530`
- `watchdog!WdLogSingleEntry0` at `0x14022957c`
- `watchdog!WdLogSingleEntry0` at `0x1402295c8`
- `watchdog!WdLogSingleEntry0` at `0x14022961c`
- `watchdog!WdLogSingleEntry0` at `0x140229674`
- `watchdog!WdLogSingleEntry0` at `0x140229843`

## string_xrefs

- `0x140229966`: `Failed to add present path (0x%I64x, 0x%I64x) to VidPN topology 0x%I64x (status = 0x%I64x)`
- `0x140229685`: `ARGUMENT_PRESENT(o_pNumVidPnPresentPathsFromSource)`

## pseudocode

```c

```
