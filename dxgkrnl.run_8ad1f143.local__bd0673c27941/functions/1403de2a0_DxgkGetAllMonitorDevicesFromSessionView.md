# DxgkGetAllMonitorDevicesFromSessionView

- ea: `0x1403de2a0`
- end: `0x1403de9d6`
- name: `DxgkGetAllMonitorDevicesFromSessionView`
- size: `1846`
- prototype: `__int64 __usercall@<rax>(struct _LUID *@<rcx>, unsigned int@<edx>, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x140367d10`

## callees

- `0x140012380`
- `0x140014f68`
- `0x140015100`
- `0x140015780`
- `0x14001b890`
- `0x14001f460`
- `0x14002ec90`
- `0x14004546c`
- `0x1400a0100`
- `0x1401bd32c`
- `0x14023cf94`
- `0x14030dc1c`
- `0x14030fcb0`
- `0x140323280`
- `0x140368514`
- `0x140383f24`
- `0x1403de2a0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de2fc`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de32e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de38a`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de2fc`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de32e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de38a`
- `watchdog!WdLogSingleEntry4` at `0x1403de3ae`
- `watchdog!WdLogSingleEntry4` at `0x1403de662`
- `watchdog!WdLogSingleEntry4` at `0x1403de71e`
- `watchdog!WdLogSingleEntry4` at `0x1403de84a`
- `watchdog!WdLogSingleEntry4` at `0x1403de8a9`
- `watchdog!WdLogSingleEntry4` at `0x1403de932`
- `watchdog!WdLogSingleEntry4` at `0x1403de3ae`
- `watchdog!WdLogSingleEntry4` at `0x1403de662`
- `watchdog!WdLogSingleEntry4` at `0x1403de71e`
- `watchdog!WdLogSingleEntry4` at `0x1403de84a`
- `watchdog!WdLogSingleEntry4` at `0x1403de8a9`
- `watchdog!WdLogSingleEntry4` at `0x1403de932`
- `watchdog!WdLogSingleEntry2` at `0x1403de318`
- `watchdog!WdLogSingleEntry2` at `0x1403de318`
- `watchdog!WdLogSingleEntry3` at `0x1403de4e7`
- `watchdog!WdLogSingleEntry3` at `0x1403de4e7`
- `watchdog!WdLogSingleEntry0` at `0x1403de3eb`
- `watchdog!WdLogSingleEntry0` at `0x1403de510`
- `watchdog!WdLogSingleEntry0` at `0x1403de59b`
- `watchdog!WdLogSingleEntry0` at `0x1403de3eb`
- `watchdog!WdLogSingleEntry0` at `0x1403de510`
- `watchdog!WdLogSingleEntry0` at `0x1403de59b`

## string_xrefs

- `0x1403de5ac`: `NT_SUCCESS(DmmEnumClientVidPnPathTargetsFromSource( pDisplaySource->GetAdapter(), pDisplaySource->GetVidPnSourceId(), 1, &VidPnTargetId)) && (VidPnTargetId == D3DDDI_ID_UNINITIALIZED)`

## pseudocode

```c

```
