# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::EndSyncFolderItems

- ea: `0x6db70`
- end: `0x6dbae`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::EndSyncFolderItems`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x7f550`

## callees

- `0x58bb0`
- `0x6db70`

## string_xrefs

- `0x6db77`: `MonitoredExchangeService.EndSyncFolderItems`
- `0x6db9c`: `MonitoredExchangeService.EndSyncFolderItems`

## pseudocode

```c

```

## disassembly

```asm
0x6db70  ldc.i4.0
0x6db71  ldarg.0
0x6db72  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6db77  ldstr    aMonitoredexcha_8// "MonitoredExchangeService.EndSyncFolderI"...
0x6db7c  ldstr    aItem_0// "Item"
0x6db81  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6db86  ldarg.0
0x6db87  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6db8c  ldarg.1
0x6db8d  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemChange> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::EndSyncFolderItems(class [mscorlib]System.IAsyncResult)
0x6db92  stloc.0
0x6db93  leave.s  loc_6DBAC
0x6db95  ldc.i4.1
0x6db96  ldarg.0
0x6db97  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6db9c  ldstr    aMonitoredexcha_8// "MonitoredExchangeService.EndSyncFolderI"...
0x6dba1  ldstr    aItem_0// "Item"
0x6dba6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dbab  endfinally
0x6dbac  ldloc.0
0x6dbad  ret
```
