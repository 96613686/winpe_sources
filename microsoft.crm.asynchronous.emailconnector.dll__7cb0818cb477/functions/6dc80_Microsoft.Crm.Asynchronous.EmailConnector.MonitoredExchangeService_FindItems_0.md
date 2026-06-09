# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::FindItems_0

- ea: `0x6dc80`
- end: `0x6dcd9`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::FindItems_0`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7c6c0`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6dc80`

## string_xrefs

- `0x6dc9c`: `MonitoredExchangeService.FindItems`
- `0x6dccb`: `MonitoredExchangeService.FindItems`

## pseudocode

```c

```

## disassembly

```asm
0x6dc80  ldarg.1
0x6dc81  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId::get_FolderName()
0x6dc86  stloc.2
0x6dc87  ldloca.s 2
0x6dc89  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName>
0x6dc8f  callvirt instance string [mscorlib]System.Object::ToString()
0x6dc94  stloc.1
0x6dc95  ldc.i4.0
0x6dc96  ldarg.0
0x6dc97  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dc9c  ldstr    aMonitoredexcha_10// "MonitoredExchangeService.FindItems"
0x6dca1  ldloc.1
0x6dca2  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dca7  ldarg.0
0x6dca8  ldarg.3
0x6dca9  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6dcae  ldarg.0
0x6dcaf  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6dcb4  ldarg.1
0x6dcb5  ldarg.2
0x6dcb6  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::FindItems(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ViewBase)
0x6dcbb  stloc.0
0x6dcbc  leave.s  loc_6DCD7
0x6dcbe  ldarg.0
0x6dcbf  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6dcc4  ldc.i4.1
0x6dcc5  ldarg.0
0x6dcc6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dccb  ldstr    aMonitoredexcha_10// "MonitoredExchangeService.FindItems"
0x6dcd0  ldloc.1
0x6dcd1  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dcd6  endfinally
0x6dcd7  ldloc.0
0x6dcd8  ret
```
