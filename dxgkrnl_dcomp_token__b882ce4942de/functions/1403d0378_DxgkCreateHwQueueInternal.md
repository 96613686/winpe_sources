# DxgkCreateHwQueueInternal

- ea: `0x1403d0378`
- end: `0x1403d0ada`
- name: `DxgkCreateHwQueueInternal`
- size: `1890`
- prototype: `__int64 __fastcall(struct _D3DKMT_CREATEHWQUEUE *)`
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x140283950`
- `0x1403d0360`

## callees

- `0x140012b14`
- `0x140013860`
- `0x140015970`
- `0x140015d70`
- `0x140016330`
- `0x14001667c`
- `0x140017fb8`
- `0x14001b890`
- `0x14001ccf0`
- `0x14001d0e4`
- `0x14001f120`
- `0x1400670a4`
- `0x1400a0100`
- `0x1401e5360`
- `0x140323854`
- `0x1403ad478`
- `0x1403bb574`
- `0x1403d0378`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1403d04c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0588`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0745`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d088e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0a64`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d04c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0588`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0745`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d088e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403d0a64`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403d0610`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403d063f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403d0610`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403d063f`
- `watchdog!WdLogSingleEntry2` at `0x1403d0629`
- `watchdog!WdLogSingleEntry2` at `0x1403d07ce`
- `watchdog!WdLogSingleEntry2` at `0x1403d0a04`
- `watchdog!WdLogSingleEntry2` at `0x1403d0629`
- `watchdog!WdLogSingleEntry2` at `0x1403d07ce`
- `watchdog!WdLogSingleEntry2` at `0x1403d0a04`
- `watchdog!WdLogSingleEntry3` at `0x1403d0556`
- `watchdog!WdLogSingleEntry3` at `0x1403d0556`
- `watchdog!WdLogSingleEntry0` at `0x1403d0496`
- `watchdog!WdLogSingleEntry0` at `0x1403d0699`
- `watchdog!WdLogSingleEntry0` at `0x1403d0496`
- `watchdog!WdLogSingleEntry0` at `0x1403d0699`
- `watchdog!WdLogSingleEntry1` at `0x1403d06e3`
- `watchdog!WdLogSingleEntry1` at `0x1403d081c`
- `watchdog!WdLogSingleEntry1` at `0x1403d0a32`
- `watchdog!WdLogSingleEntry1` at `0x1403d06e3`
- `watchdog!WdLogSingleEntry1` at `0x1403d081c`
- `watchdog!WdLogSingleEntry1` at `0x1403d0a32`

## string_xrefs

- `0x1403d0712`: `UserModeSubmission flag is deprecated, cannot create user mode submission HWQueue using DxgkCreateHwQueue. Returning 0x%I64x.`
- `0x1403d0846`: `Cannot create HW queue on context (0x%x) that doesn't support hardware queues.`
- `0x1403d06c4`: `NoKmdAccess can be used only with testsigning`

## pseudocode

```c

```
