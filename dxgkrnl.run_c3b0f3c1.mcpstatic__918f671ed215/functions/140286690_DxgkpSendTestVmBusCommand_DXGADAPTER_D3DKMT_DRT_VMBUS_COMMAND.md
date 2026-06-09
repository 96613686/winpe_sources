# DxgkpSendTestVmBusCommand(DXGADAPTER *,_D3DKMT_DRT_VMBUS_COMMAND *)

- ea: `0x140286690`
- end: `0x14028798c`
- name: `?DxgkpSendTestVmBusCommand@@YAJPEAVDXGADAPTER@@PEAU_D3DKMT_DRT_VMBUS_COMMAND@@@Z`
- size: `4860`
- prototype: `__int64 __fastcall(struct DXGADAPTER *, struct _D3DKMT_DRT_VMBUS_COMMAND *, int)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140233c10`

## callees

- `0x140012540`
- `0x1400146ac`
- `0x140015290`
- `0x140016154`
- `0x1400162a4`
- `0x14001b9c0`
- `0x14001e5b4`
- `0x1400346bc`
- `0x14004616c`
- `0x1400496ac`
- `0x14004a320`
- `0x14005f27c`
- `0x140062800`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1401c1894`
- `0x1401c1b1c`
- `0x1401e76e0`
- `0x140286690`
- `0x140288700`
- `0x1402887d0`
- `0x140329ff0`
- `0x14035f600`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140286c34`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140286eb2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402872cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140287552`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140286c34`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140286eb2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402872cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140287552`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140286f8b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140287634`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140286f8b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140287634`
- `ntoskrnl!ExFreePoolWithTag` at `0x140287925`
- `ntoskrnl!ExFreePoolWithTag` at `0x140287948`
- `ntoskrnl!ExFreePoolWithTag` at `0x140287925`
- `ntoskrnl!ExFreePoolWithTag` at `0x140287948`
- `ntoskrnl!ExAllocatePool2` at `0x1402868c7`
- `ntoskrnl!ExAllocatePool2` at `0x140286a56`
- `ntoskrnl!ExAllocatePool2` at `0x1402868c7`
- `ntoskrnl!ExAllocatePool2` at `0x140286a56`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286ab0`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286ae1`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286b3b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286b67`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286c7c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286caa`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286d2e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286d5f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286db9`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286de5`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286efa`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286f28`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287147`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287178`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402871d2`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402871fe`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287313`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287341`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402873ce`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402873ff`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287459`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287485`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028759a`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402875c8`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286ab0`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286ae1`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286b3b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286b67`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286c7c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286caa`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286d2e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286d5f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286db9`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286de5`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286efa`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140286f28`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287147`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287178`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402871d2`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402871fe`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287313`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287341`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402873ce`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402873ff`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287459`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140287485`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028759a`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402875c8`
- `ntoskrnl!ObfDereferenceObject` at `0x140286fcc`
- `ntoskrnl!ObfDereferenceObject` at `0x140287675`
- `ntoskrnl!ObfDereferenceObject` at `0x140287789`
- `ntoskrnl!ObfDereferenceObject` at `0x140286fcc`
- `ntoskrnl!ObfDereferenceObject` at `0x140287675`
- `ntoskrnl!ObfDereferenceObject` at `0x140287789`
- `ntoskrnl!ExEventObjectType` at `0x1402876dc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402876eb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402876eb`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140286bc9`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140286e47`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140287260`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x1402874e7`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140286bc9`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140286e47`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140287260`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x1402874e7`
- `watchdog!WdLogSingleEntry2` at `0x140286acb`
- `watchdog!WdLogSingleEntry2` at `0x140286b51`
- `watchdog!WdLogSingleEntry2` at `0x140286c94`
- `watchdog!WdLogSingleEntry2` at `0x140286d49`
- `watchdog!WdLogSingleEntry2` at `0x140286dcf`
- `watchdog!WdLogSingleEntry2` at `0x140286f12`
- `watchdog!WdLogSingleEntry2` at `0x140287162`
- `watchdog!WdLogSingleEntry2` at `0x1402871e8`
- `watchdog!WdLogSingleEntry2` at `0x14028732b`
- `watchdog!WdLogSingleEntry2` at `0x1402873e9`
- `watchdog!WdLogSingleEntry2` at `0x14028746f`
- `watchdog!WdLogSingleEntry2` at `0x1402875b2`
- `watchdog!WdLogSingleEntry2` at `0x140287822`
- `watchdog!WdLogSingleEntry2` at `0x140286acb`
- `watchdog!WdLogSingleEntry2` at `0x140286b51`
- `watchdog!WdLogSingleEntry2` at `0x140286c94`
- `watchdog!WdLogSingleEntry2` at `0x140286d49`
- `watchdog!WdLogSingleEntry2` at `0x140286dcf`
- `watchdog!WdLogSingleEntry2` at `0x140286f12`
- `watchdog!WdLogSingleEntry2` at `0x140287162`
- `watchdog!WdLogSingleEntry2` at `0x1402871e8`
- `watchdog!WdLogSingleEntry2` at `0x14028732b`
- `watchdog!WdLogSingleEntry2` at `0x1402873e9`
- `watchdog!WdLogSingleEntry2` at `0x14028746f`
- `watchdog!WdLogSingleEntry2` at `0x1402875b2`
- `watchdog!WdLogSingleEntry2` at `0x140287822`
- `watchdog!WdLogSingleEntry0` at `0x1402866f3`
- `watchdog!WdLogSingleEntry0` at `0x140286763`
- `watchdog!WdLogSingleEntry0` at `0x140286795`
- `watchdog!WdLogSingleEntry0` at `0x1402867c6`
- `watchdog!WdLogSingleEntry0` at `0x1402867f2`
- `watchdog!WdLogSingleEntry0` at `0x14028682f`
- `watchdog!WdLogSingleEntry0` at `0x1402868e6`
- `watchdog!WdLogSingleEntry0` at `0x14028694e`
- `watchdog!WdLogSingleEntry0` at `0x140286a2c`
- `watchdog!WdLogSingleEntry0` at `0x140286a79`
- `watchdog!WdLogSingleEntry0` at `0x140287030`
- `watchdog!WdLogSingleEntry0` at `0x140287117`
- `watchdog!WdLogSingleEntry0` at `0x140287692`
- `watchdog!WdLogSingleEntry0` at `0x140287873`
- `watchdog!WdLogSingleEntry0` at `0x1402866f3`
- `watchdog!WdLogSingleEntry0` at `0x140286763`
- `watchdog!WdLogSingleEntry0` at `0x140286795`
- `watchdog!WdLogSingleEntry0` at `0x1402867c6`
- `watchdog!WdLogSingleEntry0` at `0x1402867f2`
- `watchdog!WdLogSingleEntry0` at `0x14028682f`
- `watchdog!WdLogSingleEntry0` at `0x1402868e6`
- `watchdog!WdLogSingleEntry0` at `0x14028694e`
- `watchdog!WdLogSingleEntry0` at `0x140286a2c`
- `watchdog!WdLogSingleEntry0` at `0x140286a79`
- `watchdog!WdLogSingleEntry0` at `0x140287030`
- `watchdog!WdLogSingleEntry0` at `0x140287117`
- `watchdog!WdLogSingleEntry0` at `0x140287692`
- `watchdog!WdLogSingleEntry0` at `0x140287873`
- `watchdog!WdLogSingleEntry1` at `0x1402877ee`
- `watchdog!WdLogSingleEntry1` at `0x1402878ee`
- `watchdog!WdLogSingleEntry1` at `0x1402877ee`
- `watchdog!WdLogSingleEntry1` at `0x1402878ee`

## string_xrefs

- `0x140286704`: `NULL vmbus command`
- `0x140286991`: `Failed to read input buffer`
- `0x1402878b6`: `Failed to write output buffer`

## pseudocode

```c

```
