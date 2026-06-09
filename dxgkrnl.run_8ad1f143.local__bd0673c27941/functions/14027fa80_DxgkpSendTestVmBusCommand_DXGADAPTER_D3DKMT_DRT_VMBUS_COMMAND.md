# DxgkpSendTestVmBusCommand(DXGADAPTER *,_D3DKMT_DRT_VMBUS_COMMAND *)

- ea: `0x14027fa80`
- end: `0x140280d7c`
- name: `?DxgkpSendTestVmBusCommand@@YAJPEAVDXGADAPTER@@PEAU_D3DKMT_DRT_VMBUS_COMMAND@@@Z`
- size: `4860`
- prototype: `__int64 __fastcall(struct DXGADAPTER *, struct _D3DKMT_DRT_VMBUS_COMMAND *)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140231100`

## callees

- `0x140012380`
- `0x1400144ec`
- `0x1400150d0`
- `0x140015f94`
- `0x1400160e4`
- `0x14001b890`
- `0x14001e3e4`
- `0x1400344ec`
- `0x140045f0c`
- `0x1400494ac`
- `0x14004a120`
- `0x14005eecc`
- `0x140062450`
- `0x1400670a4`
- `0x1400a0100`
- `0x1401bec94`
- `0x1401bef1c`
- `0x1401e5360`
- `0x14027fa80`
- `0x140281af0`
- `0x140281bc0`
- `0x140323280`
- `0x14035f150`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140280024`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402802a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402806bb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140280942`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140280024`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402802a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402806bb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140280942`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028037b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140280a24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028037b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140280a24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140280d15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140280d38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140280d15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140280d38`
- `ntoskrnl!ExAllocatePool2` at `0x14027fcb7`
- `ntoskrnl!ExAllocatePool2` at `0x14027fe46`
- `ntoskrnl!ExAllocatePool2` at `0x14027fcb7`
- `ntoskrnl!ExAllocatePool2` at `0x14027fe46`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14027fea0`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14027fed1`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14027ff2b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14027ff57`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028006c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028009a`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028011e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028014f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402801a9`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402801d5`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402802ea`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280318`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280537`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280568`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402805c2`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402805ee`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280703`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280731`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402807be`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402807ef`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280849`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280875`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028098a`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402809b8`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14027fea0`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14027fed1`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14027ff2b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14027ff57`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028006c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028009a`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028011e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028014f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402801a9`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402801d5`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402802ea`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280318`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280537`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280568`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402805c2`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402805ee`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280703`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280731`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402807be`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402807ef`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280849`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140280875`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14028098a`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402809b8`
- `ntoskrnl!ObfDereferenceObject` at `0x1402803bc`
- `ntoskrnl!ObfDereferenceObject` at `0x140280a65`
- `ntoskrnl!ObfDereferenceObject` at `0x140280b79`
- `ntoskrnl!ObfDereferenceObject` at `0x1402803bc`
- `ntoskrnl!ObfDereferenceObject` at `0x140280a65`
- `ntoskrnl!ObfDereferenceObject` at `0x140280b79`
- `ntoskrnl!ExEventObjectType` at `0x140280acc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140280adb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140280adb`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x14027ffb9`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140280237`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140280650`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x1402808d7`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x14027ffb9`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140280237`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x140280650`
- `ntoskrnl!PsGetProcessDxgProcess` at `0x1402808d7`
- `watchdog!WdLogSingleEntry2` at `0x14027febb`
- `watchdog!WdLogSingleEntry2` at `0x14027ff41`
- `watchdog!WdLogSingleEntry2` at `0x140280084`
- `watchdog!WdLogSingleEntry2` at `0x140280139`
- `watchdog!WdLogSingleEntry2` at `0x1402801bf`
- `watchdog!WdLogSingleEntry2` at `0x140280302`
- `watchdog!WdLogSingleEntry2` at `0x140280552`
- `watchdog!WdLogSingleEntry2` at `0x1402805d8`
- `watchdog!WdLogSingleEntry2` at `0x14028071b`
- `watchdog!WdLogSingleEntry2` at `0x1402807d9`
- `watchdog!WdLogSingleEntry2` at `0x14028085f`
- `watchdog!WdLogSingleEntry2` at `0x1402809a2`
- `watchdog!WdLogSingleEntry2` at `0x140280c12`
- `watchdog!WdLogSingleEntry2` at `0x14027febb`
- `watchdog!WdLogSingleEntry2` at `0x14027ff41`
- `watchdog!WdLogSingleEntry2` at `0x140280084`
- `watchdog!WdLogSingleEntry2` at `0x140280139`
- `watchdog!WdLogSingleEntry2` at `0x1402801bf`
- `watchdog!WdLogSingleEntry2` at `0x140280302`
- `watchdog!WdLogSingleEntry2` at `0x140280552`
- `watchdog!WdLogSingleEntry2` at `0x1402805d8`
- `watchdog!WdLogSingleEntry2` at `0x14028071b`
- `watchdog!WdLogSingleEntry2` at `0x1402807d9`
- `watchdog!WdLogSingleEntry2` at `0x14028085f`
- `watchdog!WdLogSingleEntry2` at `0x1402809a2`
- `watchdog!WdLogSingleEntry2` at `0x140280c12`
- `watchdog!WdLogSingleEntry0` at `0x14027fae3`
- `watchdog!WdLogSingleEntry0` at `0x14027fb53`
- `watchdog!WdLogSingleEntry0` at `0x14027fb85`
- `watchdog!WdLogSingleEntry0` at `0x14027fbb6`
- `watchdog!WdLogSingleEntry0` at `0x14027fbe2`
- `watchdog!WdLogSingleEntry0` at `0x14027fc1f`
- `watchdog!WdLogSingleEntry0` at `0x14027fcd6`
- `watchdog!WdLogSingleEntry0` at `0x14027fd3e`
- `watchdog!WdLogSingleEntry0` at `0x14027fe1c`
- `watchdog!WdLogSingleEntry0` at `0x14027fe69`
- `watchdog!WdLogSingleEntry0` at `0x140280420`
- `watchdog!WdLogSingleEntry0` at `0x140280507`
- `watchdog!WdLogSingleEntry0` at `0x140280a82`
- `watchdog!WdLogSingleEntry0` at `0x140280c63`
- `watchdog!WdLogSingleEntry0` at `0x14027fae3`
- `watchdog!WdLogSingleEntry0` at `0x14027fb53`
- `watchdog!WdLogSingleEntry0` at `0x14027fb85`
- `watchdog!WdLogSingleEntry0` at `0x14027fbb6`
- `watchdog!WdLogSingleEntry0` at `0x14027fbe2`
- `watchdog!WdLogSingleEntry0` at `0x14027fc1f`
- `watchdog!WdLogSingleEntry0` at `0x14027fcd6`
- `watchdog!WdLogSingleEntry0` at `0x14027fd3e`
- `watchdog!WdLogSingleEntry0` at `0x14027fe1c`
- `watchdog!WdLogSingleEntry0` at `0x14027fe69`
- `watchdog!WdLogSingleEntry0` at `0x140280420`
- `watchdog!WdLogSingleEntry0` at `0x140280507`
- `watchdog!WdLogSingleEntry0` at `0x140280a82`
- `watchdog!WdLogSingleEntry0` at `0x140280c63`
- `watchdog!WdLogSingleEntry1` at `0x140280bde`
- `watchdog!WdLogSingleEntry1` at `0x140280cde`
- `watchdog!WdLogSingleEntry1` at `0x140280bde`
- `watchdog!WdLogSingleEntry1` at `0x140280cde`

## string_xrefs

- `0x14027faf4`: `NULL vmbus command`
- `0x14027fd81`: `Failed to read input buffer`
- `0x140280ca6`: `Failed to write output buffer`

## pseudocode

```c

```
