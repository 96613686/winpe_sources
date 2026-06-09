# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::SyncFolderItems

- ea: `0x6da70`
- end: `0x6dad7`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::SyncFolderItems`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7f340`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6da70`

## string_xrefs

- `0x6da77`: `MonitoredExchangeService.SyncFolderItems`
- `0x6dabd`: `MonitoredExchangeService.SyncFolderItems`

## pseudocode

```c

```

## disassembly

```asm
0x6da70  ldc.i4.0
0x6da71  ldarg.0
0x6da72  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6da77  ldstr    aMonitoredexcha_6// "MonitoredExchangeService.SyncFolderItem"...
0x6da7c  ldarga.s 7
0x6da7e  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6da84  callvirt instance string [mscorlib]System.Object::ToString()
0x6da89  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6da8e  ldarg.0
0x6da8f  ldarg.s  7
0x6da91  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6da96  ldarg.0
0x6da97  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6da9c  ldarg.1
0x6da9d  ldarg.2
0x6da9e  ldarg.3
0x6da9f  ldarg.s  4
0x6daa1  ldarg.s  5
0x6daa3  ldarg.s  6
0x6daa5  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemChange> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::SyncFolderItems(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SyncFolderItemsScope, string)
0x6daaa  stloc.0
0x6daab  leave.s  loc_6DAD5
0x6daad  pop
0x6daae  rethrow
0x6dab0  ldarg.0
0x6dab1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6dab6  ldc.i4.1
0x6dab7  ldarg.0
0x6dab8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dabd  ldstr    aMonitoredexcha_6// "MonitoredExchangeService.SyncFolderItem"...
0x6dac2  ldarga.s 7
0x6dac4  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6daca  callvirt instance string [mscorlib]System.Object::ToString()
0x6dacf  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dad4  endfinally
0x6dad5  ldloc.0
0x6dad6  ret
```
