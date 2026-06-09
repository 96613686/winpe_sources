# SESSION_ADAPTER::CreateCddDevice(DXGADAPTER *,DXGDEVICE * *,DXGCONTEXT * *,DXGHWQUEUE * *)

- ea: `0x140261ecc`
- end: `0x1402624ff`
- name: `?CreateCddDevice@SESSION_ADAPTER@@AEAAJPEAVDXGADAPTER@@PEAPEAVDXGDEVICE@@PEAPEAVDXGCONTEXT@@PEAPEAVDXGHWQUEUE@@@Z`
- size: `1587`
- prototype: `int(SESSION_ADAPTER *__hidden this, struct DXGADAPTER *, struct DXGDEVICE **, struct DXGCONTEXT **, struct DXGHWQUEUE **)`
- caller_count: `1`
- callee_count: `27`
- tags: ``

## callers

- `0x1402631d4`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140015780`
- `0x14001b890`
- `0x14001f460`
- `0x140021fe0`
- `0x14002dc20`
- `0x14002ec90`
- `0x140033bb0`
- `0x14003bde4`
- `0x14003cc34`
- `0x1400459e4`
- `0x1400494ac`
- `0x14004a120`
- `0x14004aad8`
- `0x1400a0100`
- `0x140261ecc`
- `0x140323854`
- `0x14034599c`
- `0x140348dd0`
- `0x14034a8b4`
- `0x1403535f0`
- `0x14035f558`
- `0x1403a4be4`
- `0x1403a4d00`
- `0x1403ab4a4`
- `0x1403ad478`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140261f5d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140261f90`
- `ntoskrnl!PsGetCurrentProcess` at `0x140262087`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402620b7`
- `ntoskrnl!PsGetCurrentProcess` at `0x140261f5d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140261f90`
- `ntoskrnl!PsGetCurrentProcess` at `0x140262087`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402620b7`
- `watchdog!WdLogSingleEntry4` at `0x140262028`
- `watchdog!WdLogSingleEntry4` at `0x1402623a3`
- `watchdog!WdLogSingleEntry4` at `0x140262028`
- `watchdog!WdLogSingleEntry4` at `0x1402623a3`
- `watchdog!WdLogSingleEntry2` at `0x140261f7a`
- `watchdog!WdLogSingleEntry2` at `0x1402621be`
- `watchdog!WdLogSingleEntry2` at `0x140261f7a`
- `watchdog!WdLogSingleEntry2` at `0x1402621be`
- `watchdog!WdLogSingleEntry3` at `0x1402620a1`
- `watchdog!WdLogSingleEntry3` at `0x14026218c`
- `watchdog!WdLogSingleEntry3` at `0x1402623cb`
- `watchdog!WdLogSingleEntry3` at `0x1402623f1`
- `watchdog!WdLogSingleEntry3` at `0x1402620a1`
- `watchdog!WdLogSingleEntry3` at `0x14026218c`
- `watchdog!WdLogSingleEntry3` at `0x1402623cb`
- `watchdog!WdLogSingleEntry3` at `0x1402623f1`
- `watchdog!WdLogSingleEntry0` at `0x140262268`
- `watchdog!WdLogSingleEntry0` at `0x140262268`
- `watchdog!WdLogSingleEntry1` at `0x140261ff4`
- `watchdog!WdLogSingleEntry1` at `0x140261ff4`

## string_xrefs

- `0x1402620cc`: `Failed to create CDD DXGDEVICE for adapter 0x%I64x in process 0x%I64x (Status = 0x%I64x).`

## pseudocode

```c

```
