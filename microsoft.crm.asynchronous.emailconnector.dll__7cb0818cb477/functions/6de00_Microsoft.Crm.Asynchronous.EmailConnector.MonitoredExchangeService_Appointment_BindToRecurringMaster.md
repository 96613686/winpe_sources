# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Appointment_BindToRecurringMaster

- ea: `0x6de00`
- end: `0x6de5f`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Appointment_BindToRecurringMaster`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x83340`
- `0x83400`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6de00`

## string_xrefs

- `0x6de07`: `MonitoredExchangeService.Appointment_BindToRecurringMaster`
- `0x6de43`: `MonitoredExchangeService.Appointment_BindToRecurringMaster`

## pseudocode

```c

```

## disassembly

```asm
0x6de00  ldc.i4.0
0x6de01  ldarg.0
0x6de02  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6de07  ldstr    aMonitoredexcha_14// "MonitoredExchangeService.Appointment_Bi"...
0x6de0c  ldc.i4.2
0x6de0d  stloc.1
0x6de0e  ldloca.s 1
0x6de10  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6de16  callvirt instance string [mscorlib]System.Object::ToString()
0x6de1b  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6de20  ldarg.0
0x6de21  ldc.i4.2
0x6de22  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6de27  ldarg.0
0x6de28  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6de2d  ldarg.1
0x6de2e  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment::BindToRecurringMaster(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId)
0x6de33  stloc.0
0x6de34  leave.s  loc_6DE5D
0x6de36  ldarg.0
0x6de37  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6de3c  ldc.i4.1
0x6de3d  ldarg.0
0x6de3e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6de43  ldstr    aMonitoredexcha_14// "MonitoredExchangeService.Appointment_Bi"...
0x6de48  ldc.i4.2
0x6de49  stloc.1
0x6de4a  ldloca.s 1
0x6de4c  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6de52  callvirt instance string [mscorlib]System.Object::ToString()
0x6de57  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6de5c  endfinally
0x6de5d  ldloc.0
0x6de5e  ret
```
