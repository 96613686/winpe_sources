# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Appointment_Update

- ea: `0x6de60`
- end: `0x6deb9`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Appointment_Update`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5f2c0`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6de60`

## string_xrefs

- `0x6de67`: `MonitoredExchangeService.Appointment_Update`
- `0x6de9e`: `MonitoredExchangeService.Appointment_Update`

## pseudocode

```c

```

## disassembly

```asm
0x6de60  ldc.i4.0
0x6de61  ldarg.0
0x6de62  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6de67  ldstr    aMonitoredexcha_15// "MonitoredExchangeService.Appointment_Up"...
0x6de6c  ldc.i4.2
0x6de6d  stloc.0
0x6de6e  ldloca.s 0
0x6de70  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6de76  callvirt instance string [mscorlib]System.Object::ToString()
0x6de7b  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6de80  ldarg.0
0x6de81  ldc.i4.2
0x6de82  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6de87  ldarg.1
0x6de88  ldarg.2
0x6de89  ldarg.3
0x6de8a  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment::Update(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ConflictResolutionMode, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SendInvitationsOrCancellationsMode)
0x6de8f  leave.s  loc_6DEB8
0x6de91  ldarg.0
0x6de92  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6de97  ldc.i4.1
0x6de98  ldarg.0
0x6de99  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6de9e  ldstr    aMonitoredexcha_15// "MonitoredExchangeService.Appointment_Up"...
0x6dea3  ldc.i4.2
0x6dea4  stloc.0
0x6dea5  ldloca.s 0
0x6dea7  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6dead  callvirt instance string [mscorlib]System.Object::ToString()
0x6deb2  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6deb7  endfinally
0x6deb8  ret
```
