# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::UpdateItems

- ea: `0x6dbb0`
- end: `0x6dc12`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::UpdateItems`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7c310`
- `0x7f740`
- `0x7f840`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6dbb0`

## string_xrefs

- `0x6dbb7`: `MonitoredExchangeService.UpdateItems`
- `0x6dbf8`: `MonitoredExchangeService.UpdateItems`

## pseudocode

```c

```

## disassembly

```asm
0x6dbb0  ldc.i4.0
0x6dbb1  ldarg.0
0x6dbb2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dbb7  ldstr    aMonitoredexcha_9// "MonitoredExchangeService.UpdateItems"
0x6dbbc  ldarga.s 6
0x6dbbe  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6dbc4  callvirt instance string [mscorlib]System.Object::ToString()
0x6dbc9  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dbce  ldarg.0
0x6dbcf  ldarg.s  6
0x6dbd1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6dbd6  ldarg.0
0x6dbd7  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6dbdc  ldarg.1
0x6dbdd  ldarg.2
0x6dbde  ldarg.3
0x6dbdf  ldarg.s  4
0x6dbe1  ldarg.s  5
0x6dbe3  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UpdateItemResponse> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::UpdateItems(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item>, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ConflictResolutionMode, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MessageDisposition>, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SendInvitationsOrCancellationsMode>)
0x6dbe8  stloc.0
0x6dbe9  leave.s  loc_6DC10
0x6dbeb  ldarg.0
0x6dbec  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6dbf1  ldc.i4.1
0x6dbf2  ldarg.0
0x6dbf3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dbf8  ldstr    aMonitoredexcha_9// "MonitoredExchangeService.UpdateItems"
0x6dbfd  ldarga.s 6
0x6dbff  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6dc05  callvirt instance string [mscorlib]System.Object::ToString()
0x6dc0a  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dc0f  endfinally
0x6dc10  ldloc.0
0x6dc11  ret
```
