# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::FindItems

- ea: `0x6dc20`
- end: `0x6dc7b`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::FindItems`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5cb00`
- `0x834d0`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6dc20`

## string_xrefs

- `0x6dc3c`: `MonitoredExchangeService.FindItems`
- `0x6dc6d`: `MonitoredExchangeService.FindItems`

## pseudocode

```c

```

## disassembly

```asm
0x6dc20  ldarg.1
0x6dc21  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId::get_FolderName()
0x6dc26  stloc.2
0x6dc27  ldloca.s 2
0x6dc29  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName>
0x6dc2f  callvirt instance string [mscorlib]System.Object::ToString()
0x6dc34  stloc.1
0x6dc35  ldc.i4.0
0x6dc36  ldarg.0
0x6dc37  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dc3c  ldstr    aMonitoredexcha_10// "MonitoredExchangeService.FindItems"
0x6dc41  ldloc.1
0x6dc42  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dc47  ldarg.0
0x6dc48  ldarg.s  4
0x6dc4a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6dc4f  ldarg.0
0x6dc50  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6dc55  ldarg.1
0x6dc56  ldarg.2
0x6dc57  ldarg.3
0x6dc58  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::FindItems(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SearchFilter, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ViewBase)
0x6dc5d  stloc.0
0x6dc5e  leave.s  loc_6DC79
0x6dc60  ldarg.0
0x6dc61  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6dc66  ldc.i4.1
0x6dc67  ldarg.0
0x6dc68  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dc6d  ldstr    aMonitoredexcha_10// "MonitoredExchangeService.FindItems"
0x6dc72  ldloc.1
0x6dc73  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dc78  endfinally
0x6dc79  ldloc.0
0x6dc7a  ret
```
