# DxgkCddGdiCommand(_DXGKCDD_SUBMITRENDERTOHWQUEUE *,char const *)

- ea: `0x140344c70`
- end: `0x140345993`
- name: `?DxgkCddGdiCommand@@YAJPEAU_DXGKCDD_SUBMITRENDERTOHWQUEUE@@PEBD@Z`
- size: `3363`
- prototype: `int(struct _DXGKCDD_SUBMITRENDERTOHWQUEUE *, const char *)`
- caller_count: `1`
- callee_count: `32`
- tags: `broker_com_uri`

## callers

- `0x1401d3720`

## callees

- `0x140012b14`
- `0x140013860`
- `0x140014790`
- `0x1400158b0`
- `0x140015970`
- `0x1400159a0`
- `0x140016300`
- `0x140016330`
- `0x140016830`
- `0x14001b890`
- `0x14001baa0`
- `0x14001c490`
- `0x14001ccf0`
- `0x14001d0e4`
- `0x14001f120`
- `0x140020150`
- `0x14002fdc0`
- `0x140033bb0`
- `0x14003bde4`
- `0x14003cc34`
- `0x1400a0100`
- `0x1400a0540`
- `0x14028c264`
- `0x1403169f4`
- `0x140323854`
- `0x140344be8`
- `0x140344c70`
- `0x14034599c`
- `0x1403459cc`
- `0x140345c50`
- `0x140346ae8`
- `0x140398124`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140345838`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034591a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140345838`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034591a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403450e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345185`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403451ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345372`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034539b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403454e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034550e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403455e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345787`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403457dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345806`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403458c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403458e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403450e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345185`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403451ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345372`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034539b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403454e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034550e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403455e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345787`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403457dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345806`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403458c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403458e9`
- `ntoskrnl!ExAllocatePool2` at `0x140345072`
- `ntoskrnl!ExAllocatePool2` at `0x140345072`
- `ntoskrnl!PsGetCurrentProcess` at `0x140344d15`
- `ntoskrnl!PsGetCurrentProcess` at `0x140344d41`
- `ntoskrnl!PsGetCurrentProcess` at `0x140344df3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140344e24`
- `ntoskrnl!PsGetCurrentProcess` at `0x140344d15`
- `ntoskrnl!PsGetCurrentProcess` at `0x140344d41`
- `ntoskrnl!PsGetCurrentProcess` at `0x140344df3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140344e24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14034582c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14034590e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14034582c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14034590e`
- `watchdog!WdLogSingleEntry2` at `0x140344d2b`
- `watchdog!WdLogSingleEntry2` at `0x140344ff3`
- `watchdog!WdLogSingleEntry2` at `0x140344d2b`
- `watchdog!WdLogSingleEntry2` at `0x140344ff3`
- `watchdog!WdLogSingleEntry3` at `0x140344e0b`
- `watchdog!WdLogSingleEntry3` at `0x140344ee5`
- `watchdog!WdLogSingleEntry3` at `0x14034549d`
- `watchdog!WdLogSingleEntry3` at `0x1403456d5`
- `watchdog!WdLogSingleEntry3` at `0x140345704`
- `watchdog!WdLogSingleEntry3` at `0x14034572d`
- `watchdog!WdLogSingleEntry3` at `0x140344e0b`
- `watchdog!WdLogSingleEntry3` at `0x140344ee5`
- `watchdog!WdLogSingleEntry3` at `0x14034549d`
- `watchdog!WdLogSingleEntry3` at `0x1403456d5`
- `watchdog!WdLogSingleEntry3` at `0x140345704`
- `watchdog!WdLogSingleEntry3` at `0x14034572d`
- `watchdog!WdLogSingleEntry0` at `0x1403450b8`
- `watchdog!WdLogSingleEntry0` at `0x140345159`
- `watchdog!WdLogSingleEntry0` at `0x1403455bd`
- `watchdog!WdLogSingleEntry0` at `0x14034588d`
- `watchdog!WdLogSingleEntry0` at `0x1403450b8`
- `watchdog!WdLogSingleEntry0` at `0x140345159`
- `watchdog!WdLogSingleEntry0` at `0x1403455bd`
- `watchdog!WdLogSingleEntry0` at `0x14034588d`
- `watchdog!WdLogSingleEntry1` at `0x1403452bf`
- `watchdog!WdLogSingleEntry1` at `0x1403452e6`
- `watchdog!WdLogSingleEntry1` at `0x140345316`
- `watchdog!WdLogSingleEntry1` at `0x1403452bf`
- `watchdog!WdLogSingleEntry1` at `0x1403452e6`
- `watchdog!WdLogSingleEntry1` at `0x140345316`

## pseudocode

```c

```
