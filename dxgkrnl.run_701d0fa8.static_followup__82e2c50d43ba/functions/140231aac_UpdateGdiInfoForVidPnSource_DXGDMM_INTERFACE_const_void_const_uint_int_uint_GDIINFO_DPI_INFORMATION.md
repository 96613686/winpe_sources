# UpdateGdiInfoForVidPnSource(_DXGDMM_INTERFACE const *,void * const,uint,int,uint,_GDIINFO *,_DPI_INFORMATION *)

- ea: `0x140231aac`
- end: `0x140232f07`
- name: `?UpdateGdiInfoForVidPnSource@@YAJPEBU_DXGDMM_INTERFACE@@QEAXIHIPEAU_GDIINFO@@PEAU_DPI_INFORMATION@@@Z`
- size: `5211`
- prototype: `int(const struct _DXGDMM_INTERFACE *, void *const, unsigned int, int, unsigned int, struct _GDIINFO *, struct _DPI_INFORMATION *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x1401e1120`

## callees

- `0x14001b9c0`
- `0x14003009c`
- `0x140030f9c`
- `0x140036fb8`
- `0x1400456cc`
- `0x140046430`
- `0x140046d28`
- `0x140047b60`
- `0x14004bf5c`
- `0x14005080c`
- `0x140054a4c`
- `0x14005f778`
- `0x140062680`
- `0x140063118`
- `0x140071a10`
- `0x140071b64`
- `0x140071d20`
- `0x140072240`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x140196118`
- `0x1401c3874`
- `0x140231154`
- `0x1402312d4`
- `0x140231658`
- `0x1402317b0`
- `0x140231874`
- `0x140231aac`
- `0x1402f45b4`
- `0x14032a5c4`
- `0x1403374e0`
- `0x1403657ac`
- `0x140368554`
- `0x1403e03c0`
- `0x1404088b4`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140231ba6`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140231ba6`
- `watchdog!WdLogSingleEntry2` at `0x140231c42`
- `watchdog!WdLogSingleEntry2` at `0x140231cd9`
- `watchdog!WdLogSingleEntry2` at `0x140231c42`
- `watchdog!WdLogSingleEntry2` at `0x140231cd9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140232ae2`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140232ae2`
- `watchdog!WdLogSingleEntry3` at `0x140231d71`
- `watchdog!WdLogSingleEntry3` at `0x14023213d`
- `watchdog!WdLogSingleEntry3` at `0x14023224b`
- `watchdog!WdLogSingleEntry3` at `0x1402323b4`
- `watchdog!WdLogSingleEntry3` at `0x140232bca`
- `watchdog!WdLogSingleEntry3` at `0x140232ccf`
- `watchdog!WdLogSingleEntry3` at `0x140232d1e`
- `watchdog!WdLogSingleEntry3` at `0x140231d71`
- `watchdog!WdLogSingleEntry3` at `0x14023213d`
- `watchdog!WdLogSingleEntry3` at `0x14023224b`
- `watchdog!WdLogSingleEntry3` at `0x1402323b4`
- `watchdog!WdLogSingleEntry3` at `0x140232bca`
- `watchdog!WdLogSingleEntry3` at `0x140232ccf`
- `watchdog!WdLogSingleEntry3` at `0x140232d1e`
- `watchdog!WdLogSingleEntry0` at `0x140231b5c`
- `watchdog!WdLogSingleEntry0` at `0x140231bba`
- `watchdog!WdLogSingleEntry0` at `0x140231e35`
- `watchdog!WdLogSingleEntry0` at `0x140231e94`
- `watchdog!WdLogSingleEntry0` at `0x140231f14`
- `watchdog!WdLogSingleEntry0` at `0x140232094`
- `watchdog!WdLogSingleEntry0` at `0x1402327fa`
- `watchdog!WdLogSingleEntry0` at `0x1402329f6`
- `watchdog!WdLogSingleEntry0` at `0x140232e38`
- `watchdog!WdLogSingleEntry0` at `0x140231b5c`
- `watchdog!WdLogSingleEntry0` at `0x140231bba`
- `watchdog!WdLogSingleEntry0` at `0x140231e35`
- `watchdog!WdLogSingleEntry0` at `0x140231e94`
- `watchdog!WdLogSingleEntry0` at `0x140231f14`
- `watchdog!WdLogSingleEntry0` at `0x140232094`
- `watchdog!WdLogSingleEntry0` at `0x1402327fa`
- `watchdog!WdLogSingleEntry0` at `0x1402329f6`
- `watchdog!WdLogSingleEntry0` at `0x140232e38`
- `watchdog!WdLogSingleEntry1` at `0x140231f61`
- `watchdog!WdLogSingleEntry1` at `0x140232612`
- `watchdog!WdLogSingleEntry1` at `0x140232b40`
- `watchdog!WdLogSingleEntry1` at `0x140231f61`
- `watchdog!WdLogSingleEntry1` at `0x140232612`
- `watchdog!WdLogSingleEntry1` at `0x140232b40`

## string_xrefs

- `0x140232d2f`: `Failed to enumerate target of %I64d'th path originating from source 0x%I64x (status = 0x%I64x)`
- `0x140232cdf`: `Failed to acquire info of path (0x%I64x, 0x%I64x) (status = 0x%I64x)`
- `0x140231d81`: `Failed to determine number of paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)`
- `0x140231c5f`: `Failed call to create copy of the last VidPN committed by the client for adapter 0x%I64x (status = 0x%I64x)`
- `0x1402320a5`: `pVidPnPresentPathInfo != NULL`

## pseudocode

```c

```
