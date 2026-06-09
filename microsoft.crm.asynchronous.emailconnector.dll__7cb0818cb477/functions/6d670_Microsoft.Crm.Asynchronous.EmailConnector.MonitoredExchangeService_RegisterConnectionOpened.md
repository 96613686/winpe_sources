# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened

- ea: `0x6d670`
- end: `0x6d737`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened`
- size: `199`
- prototype: ``
- caller_count: `16`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d7c0`
- `0x6d820`
- `0x6d880`
- `0x6d8e0`
- `0x6d940`
- `0x6d9b0`
- `0x6da70`
- `0x6dae0`
- `0x6dbb0`
- `0x6dc20`
- `0x6dc80`
- `0x6dce0`
- `0x6dd40`
- `0x6dda0`
- `0x6de00`
- `0x6de60`

## callees

- `0x7d00`
- `0x417a0`
- `0x42280`
- `0x422a0`
- `0x422b0`
- `0x422c0`
- `0x422d0`
- `0x4d8e0`
- `0x6d670`
- `0x6d740`
- `0x794b0`

## string_xrefs

- `0x6d6ab`: `Nested MonitoredExchangeService.RegisterConnectionOpened call detected. EWS connection duration perf counter values are likely to be incorrect.`

## pseudocode

```c

```

## disassembly

```asm
0x6d670  ldarg.0
0x6d671  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType> Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_currentMonitoredExchangeItemType
0x6d676  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType>::get_HasValue()
0x6d67b  brfalse.s loc_6D6BB
0x6d67d  ldarg.0
0x6d67e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d683  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x6d688  ldarg.0
0x6d689  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d68e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x6d693  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x6d698  ldarg.0
0x6d699  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d69e  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x6d6a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x6d6a8  ldc.i4.s 0x3C
0x6d6aa  ldc.i4.1
0x6d6ab  ldstr    aNestedMonitore// "Nested MonitoredExchangeService.Registe"...
0x6d6b0  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string data)
0x6d6b5  ldarg.0
0x6d6b6  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6d6bb  ldarg.0
0x6d6bc  ldarg.1
0x6d6bd  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType>::.ctor(var<u1>)
0x6d6c2  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType> Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_currentMonitoredExchangeItemType
0x6d6c7  ldarg.0
0x6d6c8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d6cd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeACTTrafficMonitor Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_NetworkTrafficMonitor()
0x6d6d2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor::RegisterConnectionOpened()
0x6d6d7  ldarg.0
0x6d6d8  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType> Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_currentMonitoredExchangeItemType
0x6d6dd  stloc.0
0x6d6de  ldloca.s 0
0x6d6e0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType>::get_HasValue()
0x6d6e5  brfalse.s loc_6D736
0x6d6e7  ldloca.s 0
0x6d6e9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType>::GetValueOrDefault()
0x6d6ee  stloc.1
0x6d6ef  ldloc.1
0x6d6f0  ldc.i4.1
0x6d6f1  sub
0x6d6f2  switch   loc_6D715, loc_6D704, loc_6D726
0x6d703  ret
0x6d704  ldarg.0
0x6d705  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d70a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentTrafficMonitor Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_AppointmentNetworkTrafficMonitor()
0x6d70f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor::RegisterConnectionOpened()
0x6d714  ret
0x6d715  ldarg.0
0x6d716  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d71b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeContactTrafficMonitor Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ContactNetworkTrafficMonitor()
0x6d720  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor::RegisterConnectionOpened()
0x6d725  ret
0x6d726  ldarg.0
0x6d727  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d72c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskTrafficMonitor Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_TaskNetworkTrafficMonitor()
0x6d731  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTrafficMonitor::RegisterConnectionOpened()
0x6d736  ret
```
