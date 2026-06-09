# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Callback

- ea: `0x6dec0`
- end: `0x6df50`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Callback`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x7d00`
- `0x417a0`
- `0x42280`
- `0x4d8c0`
- `0x4da80`
- `0x58bb0`
- `0x6d740`
- `0x6dec0`

## string_xrefs

- `0x6dec7`: `MonitoredExchangeService.Callback`
- `0x6df3f`: `MonitoredExchangeService.Callback`

## pseudocode

```c

```

## disassembly

```asm
0x6dec0  ldc.i4.0
0x6dec1  ldarg.0
0x6dec2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dec7  ldstr    aMonitoredexcha_16// "MonitoredExchangeService.Callback"
0x6decc  ldstr    aItem_0// "Item"
0x6ded1  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6ded6  ldarg.0
0x6ded7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6dedc  leave.s  loc_6DF4F
0x6dede  stloc.0
0x6dedf  ldarg.0
0x6dee0  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dee5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x6deea  ldarg.0
0x6deeb  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6def0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x6def5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x6defa  ldarg.0
0x6defb  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6df00  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x6df05  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x6df0a  ldc.i4.s 0x3C
0x6df0c  ldc.i4.1
0x6df0d  ldstr    aExceptionOccur_19// "Exception occurred while registering co"...
0x6df12  ldc.i4.1
0x6df13  newarr   [mscorlib]System.Object
0x6df18  dup
0x6df19  ldc.i4.0
0x6df1a  ldloc.0
0x6df1b  ldarg.0
0x6df1c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6df21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x6df26  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x6df2b  stelem.ref
0x6df2c  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6df31  leave.s  loc_6DF36
0x6df33  pop
0x6df34  leave.s  loc_6DF36
0x6df36  leave.s  loc_6DF4F
0x6df38  ldc.i4.1
0x6df39  ldarg.0
0x6df3a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6df3f  ldstr    aMonitoredexcha_16// "MonitoredExchangeService.Callback"
0x6df44  ldstr    aItem_0// "Item"
0x6df49  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6df4e  endfinally
0x6df4f  ret
```
