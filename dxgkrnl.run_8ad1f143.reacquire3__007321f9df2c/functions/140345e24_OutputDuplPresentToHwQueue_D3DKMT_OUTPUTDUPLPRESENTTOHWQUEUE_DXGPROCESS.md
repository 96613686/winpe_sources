# OutputDuplPresentToHwQueue(_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE *,DXGPROCESS *)

- ea: `0x140345e24`
- end: `0x140346ae0`
- name: `?OutputDuplPresentToHwQueue@@YAJPEAU_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE@@PEAVDXGPROCESS@@@Z`
- size: `3260`
- prototype: `int(struct _D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE *, struct DXGPROCESS *)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140347a90`

## callees

- `0x140012380`
- `0x140014790`
- `0x1400158b0`
- `0x140015910`
- `0x140015970`
- `0x140015a00`
- `0x140015d70`
- `0x140016330`
- `0x14001667c`
- `0x140017fb8`
- `0x1400180f0`
- `0x14001ab20`
- `0x14001b890`
- `0x14001baa0`
- `0x14001c490`
- `0x14001cbe0`
- `0x14001ccf0`
- `0x14001f120`
- `0x140020150`
- `0x140033d38`
- `0x140055044`
- `0x1400556dc`
- `0x140068954`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140344be8`
- `0x140345e24`
- `0x140347944`
- `0x140348094`
- `0x140359720`
- `0x1403752d4`
- `0x1403981a4`
- `0x1403f6568`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140346296`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403462d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346473`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403464ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034655c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346597`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346667`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403466a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403467b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403467f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403468c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346900`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346a4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346a88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346296`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403462d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346473`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403464ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034655c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346597`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346667`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403466a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403467b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403467f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403468c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346900`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346a4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346a88`
- `ntoskrnl!ExAllocatePool2` at `0x140346002`
- `ntoskrnl!ExAllocatePool2` at `0x140346002`
- `ntoskrnl!PsGetCurrentProcess` at `0x140345e9c`
- `ntoskrnl!PsGetCurrentProcess` at `0x140345e9c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140346812`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140346812`
- `watchdog!WdLogSingleEntry4` at `0x1403461dc`
- `watchdog!WdLogSingleEntry4` at `0x1403461dc`
- `watchdog!WdLogSingleEntry2` at `0x14034622a`
- `watchdog!WdLogSingleEntry2` at `0x140346758`
- `watchdog!WdLogSingleEntry2` at `0x14034622a`
- `watchdog!WdLogSingleEntry2` at `0x140346758`
- `watchdog!WdLogSingleEntry3` at `0x140345ebd`
- `watchdog!WdLogSingleEntry3` at `0x140345ebd`
- `watchdog!WdLogSingleEntry0` at `0x140345f2a`
- `watchdog!WdLogSingleEntry0` at `0x140346048`
- `watchdog!WdLogSingleEntry0` at `0x1403460d9`
- `watchdog!WdLogSingleEntry0` at `0x14034631b`
- `watchdog!WdLogSingleEntry0` at `0x14034633b`
- `watchdog!WdLogSingleEntry0` at `0x1403463f7`
- `watchdog!WdLogSingleEntry0` at `0x140345f2a`
- `watchdog!WdLogSingleEntry0` at `0x140346048`
- `watchdog!WdLogSingleEntry0` at `0x1403460d9`
- `watchdog!WdLogSingleEntry0` at `0x14034631b`
- `watchdog!WdLogSingleEntry0` at `0x14034633b`
- `watchdog!WdLogSingleEntry0` at `0x1403463f7`
- `watchdog!WdLogSingleEntry1` at `0x140345f7e`
- `watchdog!WdLogSingleEntry1` at `0x1403465d0`
- `watchdog!WdLogSingleEntry1` at `0x140346834`
- `watchdog!WdLogSingleEntry1` at `0x1403469b9`
- `watchdog!WdLogSingleEntry1` at `0x140345f7e`
- `watchdog!WdLogSingleEntry1` at `0x1403465d0`
- `watchdog!WdLogSingleEntry1` at `0x140346834`
- `watchdog!WdLogSingleEntry1` at `0x1403469b9`

## string_xrefs

- `0x140346845`: `Failed to allocate memory for present parameters. Returing 0x%I64x`

## pseudocode

```c

```
