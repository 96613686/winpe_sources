# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Item_Load

- ea: `0x6dda0`
- end: `0x6ddf4`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Item_Load`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x66490`
- `0x83390`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6dda0`

## string_xrefs

- `0x6dda7`: `MonitoredExchangeService.Item_Load`
- `0x6dddb`: `MonitoredExchangeService.Item_Load`

## pseudocode

```c

```

## disassembly

```asm
0x6dda0  ldc.i4.0
0x6dda1  ldarg.0
0x6dda2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dda7  ldstr    aMonitoredexcha_13// "MonitoredExchangeService.Item_Load"
0x6ddac  ldarga.s 3
0x6ddae  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6ddb4  callvirt instance string [mscorlib]System.Object::ToString()
0x6ddb9  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6ddbe  ldarg.0
0x6ddbf  ldarg.3
0x6ddc0  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6ddc5  ldarg.1
0x6ddc6  ldarg.2
0x6ddc7  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceObject::Load(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet)
0x6ddcc  leave.s  loc_6DDF3
0x6ddce  ldarg.0
0x6ddcf  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6ddd4  ldc.i4.1
0x6ddd5  ldarg.0
0x6ddd6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dddb  ldstr    aMonitoredexcha_13// "MonitoredExchangeService.Item_Load"
0x6dde0  ldarga.s 3
0x6dde2  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6dde8  callvirt instance string [mscorlib]System.Object::ToString()
0x6dded  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6ddf2  endfinally
0x6ddf3  ret
```
