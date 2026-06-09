# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::BindToItems

- ea: `0x6d880`
- end: `0x6d8dc`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::BindToItems`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7b660`
- `0x82f50`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6d880`

## string_xrefs

- `0x6d887`: `MonitoredExchangeService.BindToItems`
- `0x6d8c2`: `MonitoredExchangeService.BindToItems`

## pseudocode

```c

```

## disassembly

```asm
0x6d880  ldc.i4.0
0x6d881  ldarg.0
0x6d882  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d887  ldstr    aMonitoredexcha_1// "MonitoredExchangeService.BindToItems"
0x6d88c  ldarga.s 3
0x6d88e  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d894  callvirt instance string [mscorlib]System.Object::ToString()
0x6d899  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d89e  ldarg.0
0x6d89f  ldarg.3
0x6d8a0  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6d8a5  ldarg.0
0x6d8a6  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6d8ab  ldarg.1
0x6d8ac  ldarg.2
0x6d8ad  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.GetItemResponse> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::BindToItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet)
0x6d8b2  stloc.0
0x6d8b3  leave.s  loc_6D8DA
0x6d8b5  ldarg.0
0x6d8b6  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6d8bb  ldc.i4.1
0x6d8bc  ldarg.0
0x6d8bd  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d8c2  ldstr    aMonitoredexcha_1// "MonitoredExchangeService.BindToItems"
0x6d8c7  ldarga.s 3
0x6d8c9  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d8cf  callvirt instance string [mscorlib]System.Object::ToString()
0x6d8d4  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d8d9  endfinally
0x6d8da  ldloc.0
0x6d8db  ret
```
