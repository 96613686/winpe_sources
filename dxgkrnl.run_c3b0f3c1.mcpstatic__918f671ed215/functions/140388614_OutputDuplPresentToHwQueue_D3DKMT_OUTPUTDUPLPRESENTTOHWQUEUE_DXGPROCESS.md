# OutputDuplPresentToHwQueue(_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE *,DXGPROCESS *)

- ea: `0x140388614`
- end: `0x1403892d4`
- name: `?OutputDuplPresentToHwQueue@@YAJPEAU_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE@@PEAVDXGPROCESS@@@Z`
- size: `3264`
- prototype: `__int64 __fastcall(struct _D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE *, struct DXGPROCESS *)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14038a290`

## callees

- `0x140012540`
- `0x140014950`
- `0x140015a70`
- `0x140015ad0`
- `0x140015b30`
- `0x140015bc0`
- `0x140015f30`
- `0x1400164f0`
- `0x14001683c`
- `0x140018054`
- `0x140018190`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bbd0`
- `0x14001c5c0`
- `0x14001cd10`
- `0x14001ce20`
- `0x14001f2f0`
- `0x140020320`
- `0x140033f08`
- `0x1400552b4`
- `0x14005594c`
- `0x140068ea8`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x140359bd0`
- `0x140375314`
- `0x1403850e8`
- `0x1403873d8`
- `0x140388614`
- `0x14038a138`
- `0x14038a894`
- `0x1403f46e8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140388a86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388ac9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388c63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388c9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388d4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388d87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388e57`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388fa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403890b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403890f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140389241`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038927c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388a86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388ac9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388c63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388c9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388d4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388d87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388e57`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388fa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140388fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403890b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403890f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140389241`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038927c`
- `ntoskrnl!ExAllocatePool2` at `0x1403887f2`
- `ntoskrnl!ExAllocatePool2` at `0x1403887f2`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038868c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038868c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140389006`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140389006`
- `watchdog!WdLogSingleEntry4` at `0x1403889cc`
- `watchdog!WdLogSingleEntry4` at `0x1403889cc`
- `watchdog!WdLogSingleEntry2` at `0x140388a1a`
- `watchdog!WdLogSingleEntry2` at `0x140388f4c`
- `watchdog!WdLogSingleEntry2` at `0x140388a1a`
- `watchdog!WdLogSingleEntry2` at `0x140388f4c`
- `watchdog!WdLogSingleEntry3` at `0x1403886ad`
- `watchdog!WdLogSingleEntry3` at `0x1403886ad`
- `watchdog!WdLogSingleEntry0` at `0x14038871a`
- `watchdog!WdLogSingleEntry0` at `0x140388838`
- `watchdog!WdLogSingleEntry0` at `0x1403888c9`
- `watchdog!WdLogSingleEntry0` at `0x140388b0b`
- `watchdog!WdLogSingleEntry0` at `0x140388b2b`
- `watchdog!WdLogSingleEntry0` at `0x140388be7`
- `watchdog!WdLogSingleEntry0` at `0x14038871a`
- `watchdog!WdLogSingleEntry0` at `0x140388838`
- `watchdog!WdLogSingleEntry0` at `0x1403888c9`
- `watchdog!WdLogSingleEntry0` at `0x140388b0b`
- `watchdog!WdLogSingleEntry0` at `0x140388b2b`
- `watchdog!WdLogSingleEntry0` at `0x140388be7`
- `watchdog!WdLogSingleEntry1` at `0x14038876e`
- `watchdog!WdLogSingleEntry1` at `0x140388dc0`
- `watchdog!WdLogSingleEntry1` at `0x140389028`
- `watchdog!WdLogSingleEntry1` at `0x1403891ad`
- `watchdog!WdLogSingleEntry1` at `0x14038876e`
- `watchdog!WdLogSingleEntry1` at `0x140388dc0`
- `watchdog!WdLogSingleEntry1` at `0x140389028`
- `watchdog!WdLogSingleEntry1` at `0x1403891ad`

## string_xrefs

- `0x140389039`: `Failed to allocate memory for present parameters. Returing 0x%I64x`

## pseudocode

```c

```
