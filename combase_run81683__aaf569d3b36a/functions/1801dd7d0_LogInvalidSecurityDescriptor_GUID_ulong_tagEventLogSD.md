# LogInvalidSecurityDescriptor(_GUID *,ulong,tagEventLogSD)

- ea: `0x1801dd7d0`
- end: `0x1801ddb65`
- name: `?LogInvalidSecurityDescriptor@@YAXPEAU_GUID@@KW4tagEventLogSD@@@Z`
- size: `917`
- prototype: `void __fastcall(_GUID *dwID, unsigned int pAppId, tagEventLogSD dwID)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180111200`
- `0x18014b304`

## callees

- `0x1800472a0`
- `0x18005cde8`
- `0x18005ce60`
- `0x18008db2c`
- `0x1800a6f50`
- `0x180140fa0`
- `0x180153648`
- `0x18015b904`
- `0x18018cb2c`
- `0x18018d504`
- `0x18018f58c`
- `0x180194274`
- `0x1801947d8`
- `0x1801999b0`
- `0x1801dd7d0`
- `0x180209a68`
- `0x1802135dd`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1801ddabf`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1801ddabf`
- `ntdll!EtwEventRegister` at `0x1801dda85`
- `ntdll!EtwEventRegister` at `0x1801dda85`
- `ntdll!EtwEventUnregister` at `0x1801ddacc`
- `ntdll!EtwEventUnregister` at `0x1801ddacc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ddaf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ddaf4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801dd8f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801dd93e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801dd8f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801dd93e`

## string_xrefs

- `0x1801dda5a`: `onecore\com\combase\catalog\services.cxx`
- `0x1801ddb12`: `onecore\com\combase\catalog\services.cxx`
- `0x1801dda61`: `CLSID:%ws Type:%d`
- `0x1801dda4e`: `LogInvalidSecurityDescriptor`
- `0x1801ddb06`: `LogInvalidSecurityDescriptor`

## pseudocode

```c

```
