# OpenResourceFromGlobalHandleOrNtObject<_D3DKMT_OPENRESOURCE>(_D3DKMT_OPENRESOURCE *,uint,_DXGSHAREDALLOCOBJECT *,int)

- ea: `0x1403228c0`
- end: `0x1403239ed`
- name: `??$OpenResourceFromGlobalHandleOrNtObject@U_D3DKMT_OPENRESOURCE@@@@YAJPEAU_D3DKMT_OPENRESOURCE@@IPEAU_DXGSHAREDALLOCOBJECT@@H@Z`
- size: `4397`
- prototype: `__int64 __fastcall(char *Src, unsigned int)`
- caller_count: `1`
- callee_count: `41`
- tags: ``

## callers

- `0x140210d70`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x1400146ac`
- `0x140015290`
- `0x140015a70`
- `0x140015b30`
- `0x1400162a4`
- `0x1400169f0`
- `0x140018054`
- `0x14001a874`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001c790`
- `0x14001cff0`
- `0x14001d1a0`
- `0x14001e32c`
- `0x14001f2f0`
- `0x14002ef40`
- `0x1400309f0`
- `0x140034910`
- `0x14003bd18`
- `0x14003fdc8`
- `0x1400426f8`
- `0x140042854`
- `0x14004d93c`
- `0x140055fbc`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x1401e76e0`
- `0x1401e784c`
- `0x140321a2c`
- `0x1403228c0`
- `0x140324bfc`
- `0x14032a5c4`
- `0x14032aaa8`
- `0x14036fa30`
- `0x1403c2a5c`
- `0x1403da390`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140322cc8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140322cc8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140322cbc`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140322cbc`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x1403228fe`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x1403228fe`
- `watchdog!WdLogSingleEntry4` at `0x140323103`
- `watchdog!WdLogSingleEntry4` at `0x140323149`
- `watchdog!WdLogSingleEntry4` at `0x140323103`
- `watchdog!WdLogSingleEntry4` at `0x140323149`
- `watchdog!WdLogSingleEntry2` at `0x140322a5d`
- `watchdog!WdLogSingleEntry2` at `0x140322ac8`
- `watchdog!WdLogSingleEntry2` at `0x140322b53`
- `watchdog!WdLogSingleEntry2` at `0x140322d6b`
- `watchdog!WdLogSingleEntry2` at `0x140322e7c`
- `watchdog!WdLogSingleEntry2` at `0x14032318d`
- `watchdog!WdLogSingleEntry2` at `0x1403238be`
- `watchdog!WdLogSingleEntry2` at `0x140323941`
- `watchdog!WdLogSingleEntry2` at `0x140322a5d`
- `watchdog!WdLogSingleEntry2` at `0x140322ac8`
- `watchdog!WdLogSingleEntry2` at `0x140322b53`
- `watchdog!WdLogSingleEntry2` at `0x140322d6b`
- `watchdog!WdLogSingleEntry2` at `0x140322e7c`
- `watchdog!WdLogSingleEntry2` at `0x14032318d`
- `watchdog!WdLogSingleEntry2` at `0x1403238be`
- `watchdog!WdLogSingleEntry2` at `0x140323941`
- `watchdog!WdLogSingleEntry3` at `0x140322cf8`
- `watchdog!WdLogSingleEntry3` at `0x140322f36`
- `watchdog!WdLogSingleEntry3` at `0x140322fa8`
- `watchdog!WdLogSingleEntry3` at `0x140323002`
- `watchdog!WdLogSingleEntry3` at `0x14032305a`
- `watchdog!WdLogSingleEntry3` at `0x14032340a`
- `watchdog!WdLogSingleEntry3` at `0x14032390a`
- `watchdog!WdLogSingleEntry3` at `0x140322cf8`
- `watchdog!WdLogSingleEntry3` at `0x140322f36`
- `watchdog!WdLogSingleEntry3` at `0x140322fa8`
- `watchdog!WdLogSingleEntry3` at `0x140323002`
- `watchdog!WdLogSingleEntry3` at `0x14032305a`
- `watchdog!WdLogSingleEntry3` at `0x14032340a`
- `watchdog!WdLogSingleEntry3` at `0x14032390a`
- `watchdog!WdLogSingleEntry0` at `0x140322c4d`
- `watchdog!WdLogSingleEntry0` at `0x1403236ba`
- `watchdog!WdLogSingleEntry0` at `0x140323778`
- `watchdog!WdLogSingleEntry0` at `0x140322c4d`
- `watchdog!WdLogSingleEntry0` at `0x1403236ba`
- `watchdog!WdLogSingleEntry0` at `0x140323778`
- `watchdog!WdLogSingleEntry1` at `0x140322935`
- `watchdog!WdLogSingleEntry1` at `0x1403229cf`
- `watchdog!WdLogSingleEntry1` at `0x140323514`
- `watchdog!WdLogSingleEntry1` at `0x140323578`
- `watchdog!WdLogSingleEntry1` at `0x1403235d9`
- `watchdog!WdLogSingleEntry1` at `0x140323641`
- `watchdog!WdLogSingleEntry1` at `0x140323681`
- `watchdog!WdLogSingleEntry1` at `0x140322935`
- `watchdog!WdLogSingleEntry1` at `0x1403229cf`
- `watchdog!WdLogSingleEntry1` at `0x140323514`
- `watchdog!WdLogSingleEntry1` at `0x140323578`
- `watchdog!WdLogSingleEntry1` at `0x1403235d9`
- `watchdog!WdLogSingleEntry1` at `0x140323641`
- `watchdog!WdLogSingleEntry1` at `0x140323681`

## pseudocode

```c

```
