# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Item_Bind

- ea: `0x6dd40`
- end: `0x6dd9c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Item_Bind`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x83440`
- `0x84060`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6dd40`

## string_xrefs

- `0x6dd47`: `MonitoredExchangeService.Item_Bind`
- `0x6dd82`: `MonitoredExchangeService.Item_Bind`

## pseudocode

```c

```

## disassembly

```asm
0x6dd40  ldc.i4.0
0x6dd41  ldarg.0
0x6dd42  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dd47  ldstr    aMonitoredexcha_12// "MonitoredExchangeService.Item_Bind"
0x6dd4c  ldarga.s 3
0x6dd4e  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6dd54  callvirt instance string [mscorlib]System.Object::ToString()
0x6dd59  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dd5e  ldarg.0
0x6dd5f  ldarg.3
0x6dd60  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6dd65  ldarg.0
0x6dd66  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6dd6b  ldarg.1
0x6dd6c  ldarg.2
0x6dd6d  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::Bind(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet)
0x6dd72  stloc.0
0x6dd73  leave.s  loc_6DD9A
0x6dd75  ldarg.0
0x6dd76  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6dd7b  ldc.i4.1
0x6dd7c  ldarg.0
0x6dd7d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dd82  ldstr    aMonitoredexcha_12// "MonitoredExchangeService.Item_Bind"
0x6dd87  ldarga.s 3
0x6dd89  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6dd8f  callvirt instance string [mscorlib]System.Object::ToString()
0x6dd94  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dd99  endfinally
0x6dd9a  ldloc.0
0x6dd9b  ret
```
