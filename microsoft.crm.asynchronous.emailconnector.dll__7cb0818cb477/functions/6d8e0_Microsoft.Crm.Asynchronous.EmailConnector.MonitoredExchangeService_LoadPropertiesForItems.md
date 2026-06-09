# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::LoadPropertiesForItems

- ea: `0x6d8e0`
- end: `0x6d93c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::LoadPropertiesForItems`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7da50`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6d8e0`

## string_xrefs

- `0x6d8e7`: `MonitoredExchangeService.LoadPropertiesForItems`
- `0x6d922`: `MonitoredExchangeService.LoadPropertiesForItems`

## pseudocode

```c

```

## disassembly

```asm
0x6d8e0  ldc.i4.0
0x6d8e1  ldarg.0
0x6d8e2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d8e7  ldstr    aMonitoredexcha_2// "MonitoredExchangeService.LoadProperties"...
0x6d8ec  ldarga.s 3
0x6d8ee  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d8f4  callvirt instance string [mscorlib]System.Object::ToString()
0x6d8f9  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d8fe  ldarg.0
0x6d8ff  ldarg.3
0x6d900  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6d905  ldarg.0
0x6d906  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6d90b  ldarg.1
0x6d90c  ldarg.2
0x6d90d  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::LoadPropertiesForItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet)
0x6d912  stloc.0
0x6d913  leave.s  loc_6D93A
0x6d915  ldarg.0
0x6d916  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6d91b  ldc.i4.1
0x6d91c  ldarg.0
0x6d91d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d922  ldstr    aMonitoredexcha_2// "MonitoredExchangeService.LoadProperties"...
0x6d927  ldarga.s 3
0x6d929  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d92f  callvirt instance string [mscorlib]System.Object::ToString()
0x6d934  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d939  endfinally
0x6d93a  ldloc.0
0x6d93b  ret
```
