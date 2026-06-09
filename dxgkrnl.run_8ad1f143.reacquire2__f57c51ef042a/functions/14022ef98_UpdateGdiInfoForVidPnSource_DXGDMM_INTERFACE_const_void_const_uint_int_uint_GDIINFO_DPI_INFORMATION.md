# UpdateGdiInfoForVidPnSource(_DXGDMM_INTERFACE const *,void * const,uint,int,uint,_GDIINFO *,_DPI_INFORMATION *)

- ea: `0x14022ef98`
- end: `0x1402303f3`
- name: `?UpdateGdiInfoForVidPnSource@@YAJPEBU_DXGDMM_INTERFACE@@QEAXIHIPEAU_GDIINFO@@PEAU_DPI_INFORMATION@@@Z`
- size: `5211`
- prototype: `int(const struct _DXGDMM_INTERFACE *, void *const, unsigned int, int, unsigned int, struct _GDIINFO *, struct _DPI_INFORMATION *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x1401dedb0`

## callees

- `0x14001b890`
- `0x14002fecc`
- `0x140030dcc`
- `0x140036de8`
- `0x14004546c`
- `0x1400461d0`
- `0x140046ac8`
- `0x140047960`
- `0x14004bd5c`
- `0x14005064c`
- `0x14005486c`
- `0x14005f3c8`
- `0x1400622d0`
- `0x140062cf8`
- `0x1400713d0`
- `0x140071524`
- `0x1400716e0`
- `0x140071c00`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140192114`
- `0x1401c0c74`
- `0x14022e640`
- `0x14022e7c0`
- `0x14022eb44`
- `0x14022ec9c`
- `0x14022ed60`
- `0x14022ef98`
- `0x1402edb04`
- `0x140323854`
- `0x140330ac0`
- `0x14036576c`
- `0x140368514`
- `0x1403dffa0`
- `0x140409564`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14022f092`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14022f092`
- `watchdog!WdLogSingleEntry2` at `0x14022f12e`
- `watchdog!WdLogSingleEntry2` at `0x14022f1c5`
- `watchdog!WdLogSingleEntry2` at `0x14022f12e`
- `watchdog!WdLogSingleEntry2` at `0x14022f1c5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14022ffce`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14022ffce`
- `watchdog!WdLogSingleEntry3` at `0x14022f25d`
- `watchdog!WdLogSingleEntry3` at `0x14022f629`
- `watchdog!WdLogSingleEntry3` at `0x14022f737`
- `watchdog!WdLogSingleEntry3` at `0x14022f8a0`
- `watchdog!WdLogSingleEntry3` at `0x1402300b6`
- `watchdog!WdLogSingleEntry3` at `0x1402301bb`
- `watchdog!WdLogSingleEntry3` at `0x14023020a`
- `watchdog!WdLogSingleEntry3` at `0x14022f25d`
- `watchdog!WdLogSingleEntry3` at `0x14022f629`
- `watchdog!WdLogSingleEntry3` at `0x14022f737`
- `watchdog!WdLogSingleEntry3` at `0x14022f8a0`
- `watchdog!WdLogSingleEntry3` at `0x1402300b6`
- `watchdog!WdLogSingleEntry3` at `0x1402301bb`
- `watchdog!WdLogSingleEntry3` at `0x14023020a`
- `watchdog!WdLogSingleEntry0` at `0x14022f048`
- `watchdog!WdLogSingleEntry0` at `0x14022f0a6`
- `watchdog!WdLogSingleEntry0` at `0x14022f321`
- `watchdog!WdLogSingleEntry0` at `0x14022f380`
- `watchdog!WdLogSingleEntry0` at `0x14022f400`
- `watchdog!WdLogSingleEntry0` at `0x14022f580`
- `watchdog!WdLogSingleEntry0` at `0x14022fce6`
- `watchdog!WdLogSingleEntry0` at `0x14022fee2`
- `watchdog!WdLogSingleEntry0` at `0x140230324`
- `watchdog!WdLogSingleEntry0` at `0x14022f048`
- `watchdog!WdLogSingleEntry0` at `0x14022f0a6`
- `watchdog!WdLogSingleEntry0` at `0x14022f321`
- `watchdog!WdLogSingleEntry0` at `0x14022f380`
- `watchdog!WdLogSingleEntry0` at `0x14022f400`
- `watchdog!WdLogSingleEntry0` at `0x14022f580`
- `watchdog!WdLogSingleEntry0` at `0x14022fce6`
- `watchdog!WdLogSingleEntry0` at `0x14022fee2`
- `watchdog!WdLogSingleEntry0` at `0x140230324`
- `watchdog!WdLogSingleEntry1` at `0x14022f44d`
- `watchdog!WdLogSingleEntry1` at `0x14022fafe`
- `watchdog!WdLogSingleEntry1` at `0x14023002c`
- `watchdog!WdLogSingleEntry1` at `0x14022f44d`
- `watchdog!WdLogSingleEntry1` at `0x14022fafe`
- `watchdog!WdLogSingleEntry1` at `0x14023002c`

## string_xrefs

- `0x14023021b`: `Failed to enumerate target of %I64d'th path originating from source 0x%I64x (status = 0x%I64x)`
- `0x1402301cb`: `Failed to acquire info of path (0x%I64x, 0x%I64x) (status = 0x%I64x)`
- `0x14022f26d`: `Failed to determine number of paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)`
- `0x14022f14b`: `Failed call to create copy of the last VidPN committed by the client for adapter 0x%I64x (status = 0x%I64x)`
- `0x14022f591`: `pVidPnPresentPathInfo != NULL`

## pseudocode

```c

```
