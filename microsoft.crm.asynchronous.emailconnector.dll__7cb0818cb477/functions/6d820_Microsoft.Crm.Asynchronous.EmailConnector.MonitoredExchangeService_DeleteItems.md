# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::DeleteItems

- ea: `0x6d820`
- end: `0x6d880`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::DeleteItems`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7be00`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6d820`

## string_xrefs

- `0x6d827`: `MonitoredExchangeService.DeleteItems`
- `0x6d866`: `MonitoredExchangeService.DeleteItems`

## pseudocode

```c

```

## disassembly

```asm
0x6d820  ldc.i4.0
0x6d821  ldarg.0
0x6d822  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d827  ldstr    aMonitoredexcha_0// "MonitoredExchangeService.DeleteItems"
0x6d82c  ldarga.s 5
0x6d82e  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d834  callvirt instance string [mscorlib]System.Object::ToString()
0x6d839  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d83e  ldarg.0
0x6d83f  ldarg.s  5
0x6d841  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6d846  ldarg.0
0x6d847  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6d84c  ldarg.1
0x6d84d  ldarg.2
0x6d84e  ldarg.3
0x6d84f  ldarg.s  4
0x6d851  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponse> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::DeleteItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DeleteMode, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SendCancellationsMode>, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.AffectedTaskOccurrence>)
0x6d856  stloc.0
0x6d857  leave.s  loc_6D87E
0x6d859  ldarg.0
0x6d85a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6d85f  ldc.i4.1
0x6d860  ldarg.0
0x6d861  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d866  ldstr    aMonitoredexcha_0// "MonitoredExchangeService.DeleteItems"
0x6d86b  ldarga.s 5
0x6d86d  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d873  callvirt instance string [mscorlib]System.Object::ToString()
0x6d878  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d87d  endfinally
0x6d87e  ldloc.0
0x6d87f  ret
```
