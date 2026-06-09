# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::CreateItems

- ea: `0x6d7c0`
- end: `0x6d820`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::CreateItems`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7b950`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6d7c0`

## string_xrefs

- `0x6d7c7`: `MonitoredExchangeService.CreateItems`
- `0x6d806`: `MonitoredExchangeService.CreateItems`

## pseudocode

```c

```

## disassembly

```asm
0x6d7c0  ldc.i4.0
0x6d7c1  ldarg.0
0x6d7c2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d7c7  ldstr    aMonitoredexcha// "MonitoredExchangeService.CreateItems"
0x6d7cc  ldarga.s 5
0x6d7ce  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d7d4  callvirt instance string [mscorlib]System.Object::ToString()
0x6d7d9  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d7de  ldarg.0
0x6d7df  ldarg.s  5
0x6d7e1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6d7e6  ldarg.0
0x6d7e7  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6d7ec  ldarg.1
0x6d7ed  ldarg.2
0x6d7ee  ldarg.3
0x6d7ef  ldarg.s  4
0x6d7f1  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::CreateItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MessageDisposition>, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SendInvitationsMode>)
0x6d7f6  stloc.0
0x6d7f7  leave.s  loc_6D81E
0x6d7f9  ldarg.0
0x6d7fa  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6d7ff  ldc.i4.1
0x6d800  ldarg.0
0x6d801  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d806  ldstr    aMonitoredexcha// "MonitoredExchangeService.CreateItems"
0x6d80b  ldarga.s 5
0x6d80d  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d813  callvirt instance string [mscorlib]System.Object::ToString()
0x6d818  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d81d  endfinally
0x6d81e  ldloc.0
0x6d81f  ret
```
