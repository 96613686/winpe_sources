# DxgkGetAllMonitorDevicesFromSessionView

- ea: `0x1403de6c0`
- end: `0x1403dedf6`
- name: `DxgkGetAllMonitorDevicesFromSessionView`
- size: `1846`
- prototype: `__int64 __fastcall(struct _LUID *, unsigned int, bool *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x140367d50`

## callees

- `0x140012540`
- `0x140015128`
- `0x1400152c0`
- `0x140015940`
- `0x14001b9c0`
- `0x14001f630`
- `0x14002ee60`
- `0x1400456cc`
- `0x1400a0bd0`
- `0x1401bff2c`
- `0x14023faf4`
- `0x14031498c`
- `0x140316a28`
- `0x140329ff0`
- `0x14034b0a4`
- `0x140368554`
- `0x1403de6c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de71c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de74e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de7aa`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de71c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de74e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403de7aa`
- `watchdog!WdLogSingleEntry4` at `0x1403de7ce`
- `watchdog!WdLogSingleEntry4` at `0x1403dea82`
- `watchdog!WdLogSingleEntry4` at `0x1403deb3e`
- `watchdog!WdLogSingleEntry4` at `0x1403dec6a`
- `watchdog!WdLogSingleEntry4` at `0x1403decc9`
- `watchdog!WdLogSingleEntry4` at `0x1403ded52`
- `watchdog!WdLogSingleEntry4` at `0x1403de7ce`
- `watchdog!WdLogSingleEntry4` at `0x1403dea82`
- `watchdog!WdLogSingleEntry4` at `0x1403deb3e`
- `watchdog!WdLogSingleEntry4` at `0x1403dec6a`
- `watchdog!WdLogSingleEntry4` at `0x1403decc9`
- `watchdog!WdLogSingleEntry4` at `0x1403ded52`
- `watchdog!WdLogSingleEntry2` at `0x1403de738`
- `watchdog!WdLogSingleEntry2` at `0x1403de738`
- `watchdog!WdLogSingleEntry3` at `0x1403de907`
- `watchdog!WdLogSingleEntry3` at `0x1403de907`
- `watchdog!WdLogSingleEntry0` at `0x1403de80b`
- `watchdog!WdLogSingleEntry0` at `0x1403de930`
- `watchdog!WdLogSingleEntry0` at `0x1403de9bb`
- `watchdog!WdLogSingleEntry0` at `0x1403de80b`
- `watchdog!WdLogSingleEntry0` at `0x1403de930`
- `watchdog!WdLogSingleEntry0` at `0x1403de9bb`

## string_xrefs

- `0x1403de9cc`: `NT_SUCCESS(DmmEnumClientVidPnPathTargetsFromSource( pDisplaySource->GetAdapter(), pDisplaySource->GetVidPnSourceId(), 1, &VidPnTargetId)) && (VidPnTargetId == D3DDDI_ID_UNINITIALIZED)`

## pseudocode

```c

```
