# SESSION_ADAPTER::CreateCddDevice(DXGADAPTER *,DXGDEVICE * *,DXGCONTEXT * *,DXGHWQUEUE * *)

- ea: `0x14026748c`
- end: `0x140267abf`
- name: `?CreateCddDevice@SESSION_ADAPTER@@AEAAJPEAVDXGADAPTER@@PEAPEAVDXGDEVICE@@PEAPEAVDXGCONTEXT@@PEAPEAVDXGHWQUEUE@@@Z`
- size: `1587`
- prototype: `int(SESSION_ADAPTER *__hidden this, struct DXGADAPTER *, struct DXGDEVICE **, struct DXGCONTEXT **, struct DXGHWQUEUE **)`
- caller_count: `1`
- callee_count: `27`
- tags: ``

## callers

- `0x140268794`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140015940`
- `0x14001b9c0`
- `0x14001f630`
- `0x1400221b0`
- `0x14002ddf0`
- `0x14002ee60`
- `0x140033d80`
- `0x14003c044`
- `0x14003ce94`
- `0x140045c44`
- `0x1400496ac`
- `0x14004a320`
- `0x14004acd8`
- `0x1400a0bd0`
- `0x14026748c`
- `0x14032a5c4`
- `0x14033ebec`
- `0x1403406d0`
- `0x140353aa0`
- `0x14035fa08`
- `0x14038818c`
- `0x1403a59c4`
- `0x1403a5ae0`
- `0x1403ac284`
- `0x1403b70c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14026751d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267550`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267647`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267677`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026751d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267550`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267647`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267677`
- `watchdog!WdLogSingleEntry4` at `0x1402675e8`
- `watchdog!WdLogSingleEntry4` at `0x140267963`
- `watchdog!WdLogSingleEntry4` at `0x1402675e8`
- `watchdog!WdLogSingleEntry4` at `0x140267963`
- `watchdog!WdLogSingleEntry2` at `0x14026753a`
- `watchdog!WdLogSingleEntry2` at `0x14026777e`
- `watchdog!WdLogSingleEntry2` at `0x14026753a`
- `watchdog!WdLogSingleEntry2` at `0x14026777e`
- `watchdog!WdLogSingleEntry3` at `0x140267661`
- `watchdog!WdLogSingleEntry3` at `0x14026774c`
- `watchdog!WdLogSingleEntry3` at `0x14026798b`
- `watchdog!WdLogSingleEntry3` at `0x1402679b1`
- `watchdog!WdLogSingleEntry3` at `0x140267661`
- `watchdog!WdLogSingleEntry3` at `0x14026774c`
- `watchdog!WdLogSingleEntry3` at `0x14026798b`
- `watchdog!WdLogSingleEntry3` at `0x1402679b1`
- `watchdog!WdLogSingleEntry0` at `0x140267828`
- `watchdog!WdLogSingleEntry0` at `0x140267828`
- `watchdog!WdLogSingleEntry1` at `0x1402675b4`
- `watchdog!WdLogSingleEntry1` at `0x1402675b4`

## string_xrefs

- `0x14026768c`: `Failed to create CDD DXGDEVICE for adapter 0x%I64x in process 0x%I64x (Status = 0x%I64x).`

## pseudocode

```c

```
