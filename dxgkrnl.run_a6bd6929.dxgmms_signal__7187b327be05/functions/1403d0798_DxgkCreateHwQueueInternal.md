# DxgkCreateHwQueueInternal

- ea: `0x1403d0798`
- end: `0x1403d0efa`
- name: `DxgkCreateHwQueueInternal`
- size: `1890`
- prototype: `__int64 __fastcall(struct _D3DKMT_CREATEHWQUEUE *)`
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x14028a560`
- `0x1403d0780`

## callees

- `0x140012cd4`
- `0x140013a20`
- `0x140015b30`
- `0x140015f30`
- `0x1400164f0`
- `0x14001683c`
- `0x140018054`
- `0x14001b9c0`
- `0x14001ce20`
- `0x14001d214`
- `0x14001f2f0`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1401e76e0`
- `0x14032a5c4`
- `0x1403b70c0`
- `0x1403ba894`
- `0x1403d0798`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1403d08e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d09a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0b65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0cae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0e84`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d08e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d09a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0b65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0cae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0e84`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403d0a30`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403d0a5f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403d0a30`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403d0a5f`
- `watchdog!WdLogSingleEntry2` at `0x1403d0a49`
- `watchdog!WdLogSingleEntry2` at `0x1403d0bee`
- `watchdog!WdLogSingleEntry2` at `0x1403d0e24`
- `watchdog!WdLogSingleEntry2` at `0x1403d0a49`
- `watchdog!WdLogSingleEntry2` at `0x1403d0bee`
- `watchdog!WdLogSingleEntry2` at `0x1403d0e24`
- `watchdog!WdLogSingleEntry3` at `0x1403d0976`
- `watchdog!WdLogSingleEntry3` at `0x1403d0976`
- `watchdog!WdLogSingleEntry0` at `0x1403d08b6`
- `watchdog!WdLogSingleEntry0` at `0x1403d0ab9`
- `watchdog!WdLogSingleEntry0` at `0x1403d08b6`
- `watchdog!WdLogSingleEntry0` at `0x1403d0ab9`
- `watchdog!WdLogSingleEntry1` at `0x1403d0b03`
- `watchdog!WdLogSingleEntry1` at `0x1403d0c3c`
- `watchdog!WdLogSingleEntry1` at `0x1403d0e52`
- `watchdog!WdLogSingleEntry1` at `0x1403d0b03`
- `watchdog!WdLogSingleEntry1` at `0x1403d0c3c`
- `watchdog!WdLogSingleEntry1` at `0x1403d0e52`

## string_xrefs

- `0x1403d0b32`: `UserModeSubmission flag is deprecated, cannot create user mode submission HWQueue using DxgkCreateHwQueue. Returning 0x%I64x.`
- `0x1403d0c66`: `Cannot create HW queue on context (0x%x) that doesn't support hardware queues.`
- `0x1403d0ae4`: `NoKmdAccess can be used only with testsigning`

## pseudocode

```c

```
