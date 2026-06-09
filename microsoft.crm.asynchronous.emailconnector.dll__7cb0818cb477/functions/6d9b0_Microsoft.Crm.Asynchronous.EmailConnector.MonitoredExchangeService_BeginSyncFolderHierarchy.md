# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::BeginSyncFolderHierarchy

- ea: `0x6d9b0`
- end: `0x6da2d`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::BeginSyncFolderHierarchy`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7f020`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6d9b0`

## string_xrefs

- `0x6d9b7`: `MonitoredExchangeService.BeginSyncFolderHierarchy`
- `0x6da13`: `MonitoredExchangeService.BeginSyncFolderHierarchy`

## pseudocode

```c

```

## disassembly

```asm
0x6d9b0  ldc.i4.0
0x6d9b1  ldarg.0
0x6d9b2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d9b7  ldstr    aMonitoredexcha_4// "MonitoredExchangeService.BeginSyncFolde"...
0x6d9bc  ldarga.s 6
0x6d9be  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d9c4  callvirt instance string [mscorlib]System.Object::ToString()
0x6d9c9  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d9ce  ldarg.0
0x6d9cf  ldftn    instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Callback(class [mscorlib]System.IAsyncResult asyncResult)
0x6d9d5  newobj   instance void [mscorlib]System.AsyncCallback::.ctor(object, native int)
0x6d9da  ldarg.1
0x6d9db  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x6d9e0  castclass [mscorlib]System.AsyncCallback
0x6d9e5  stloc.1
0x6d9e6  ldarg.0
0x6d9e7  ldarg.s  6
0x6d9e9  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6d9ee  ldarg.0
0x6d9ef  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6d9f4  ldloc.1
0x6d9f5  ldarg.2
0x6d9f6  ldarg.3
0x6d9f7  ldarg.s  4
0x6d9f9  ldarg.s  5
0x6d9fb  callvirt instance class [mscorlib]System.IAsyncResult [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::BeginSyncFolderHierarchy(class [mscorlib]System.AsyncCallback, object, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet, string)
0x6da00  stloc.0
0x6da01  leave.s  loc_6DA2B
0x6da03  pop
0x6da04  ldarg.0
0x6da05  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6da0a  rethrow
0x6da0c  ldc.i4.1
0x6da0d  ldarg.0
0x6da0e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6da13  ldstr    aMonitoredexcha_4// "MonitoredExchangeService.BeginSyncFolde"...
0x6da18  ldarga.s 6
0x6da1a  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6da20  callvirt instance string [mscorlib]System.Object::ToString()
0x6da25  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6da2a  endfinally
0x6da2b  ldloc.0
0x6da2c  ret
```
