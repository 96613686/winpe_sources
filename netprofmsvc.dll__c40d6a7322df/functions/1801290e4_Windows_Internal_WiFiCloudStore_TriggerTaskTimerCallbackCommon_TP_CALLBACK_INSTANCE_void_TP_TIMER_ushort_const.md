# Windows::Internal::WiFiCloudStore::TriggerTaskTimerCallbackCommon(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *,ushort const *)

- ea: `0x1801290e4`
- end: `0x180129175`
- name: `?TriggerTaskTimerCallbackCommon@WiFiCloudStore@Internal@Windows@@YAJPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@PEBG@Z`
- size: `145`
- prototype: `int(Windows::Internal::WiFiCloudStore *__hidden this, struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180129180`

## callees

- `0x180015628`
- `0x180099c64`
- `0x1801290c4`
- `0x1801290e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x1801290f6`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x1801290f6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012914e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180129156`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012914e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180129156`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180129100`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180129100`

## string_xrefs

- `0x180129111`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x18012913a`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`

## pseudocode

```c

```
