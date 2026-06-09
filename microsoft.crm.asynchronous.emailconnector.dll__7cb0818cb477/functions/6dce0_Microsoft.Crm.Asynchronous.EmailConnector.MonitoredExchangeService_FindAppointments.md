# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::FindAppointments

- ea: `0x6dce0`
- end: `0x6dd3c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::FindAppointments`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x83300`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6dce0`

## string_xrefs

- `0x6dce7`: `MonitoredExchangeService.FindAppointments`
- `0x6dd22`: `MonitoredExchangeService.FindAppointments`

## pseudocode

```c

```

## disassembly

```asm
0x6dce0  ldc.i4.0
0x6dce1  ldarg.0
0x6dce2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dce7  ldstr    aMonitoredexcha_11// "MonitoredExchangeService.FindAppointmen"...
0x6dcec  ldarga.s 1
0x6dcee  constrained. [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName
0x6dcf4  callvirt instance string [mscorlib]System.Object::ToString()
0x6dcf9  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dcfe  ldarg.0
0x6dcff  ldc.i4.2
0x6dd00  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6dd05  ldarg.0
0x6dd06  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6dd0b  ldarg.1
0x6dd0c  ldarg.2
0x6dd0d  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FindItemsResults`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::FindAppointments(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.CalendarView)
0x6dd12  stloc.0
0x6dd13  leave.s  loc_6DD3A
0x6dd15  ldarg.0
0x6dd16  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6dd1b  ldc.i4.1
0x6dd1c  ldarg.0
0x6dd1d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dd22  ldstr    aMonitoredexcha_11// "MonitoredExchangeService.FindAppointmen"...
0x6dd27  ldarga.s 1
0x6dd29  constrained. [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName
0x6dd2f  callvirt instance string [mscorlib]System.Object::ToString()
0x6dd34  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dd39  endfinally
0x6dd3a  ldloc.0
0x6dd3b  ret
```
