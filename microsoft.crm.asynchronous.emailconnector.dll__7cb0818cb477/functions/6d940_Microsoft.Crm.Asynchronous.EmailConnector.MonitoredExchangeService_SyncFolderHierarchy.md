# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::SyncFolderHierarchy

- ea: `0x6d940`
- end: `0x6d9a1`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::SyncFolderHierarchy`
- size: `97`
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
- `0x6d940`

## string_xrefs

- `0x6d947`: `MonitoredExchangeService.SyncFolderHierarchy`
- `0x6d987`: `MonitoredExchangeService.SyncFolderHierarchy`

## pseudocode

```c

```

## disassembly

```asm
0x6d940  ldc.i4.0
0x6d941  ldarg.0
0x6d942  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d947  ldstr    aMonitoredexcha_3// "MonitoredExchangeService.SyncFolderHier"...
0x6d94c  ldarga.s 4
0x6d94e  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d954  callvirt instance string [mscorlib]System.Object::ToString()
0x6d959  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d95e  ldarg.0
0x6d95f  ldarg.s  4
0x6d961  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6d966  ldarg.0
0x6d967  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6d96c  ldarg.1
0x6d96d  ldarg.2
0x6d96e  ldarg.3
0x6d96f  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::SyncFolderHierarchy(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet, string)
0x6d974  stloc.0
0x6d975  leave.s  loc_6D99F
0x6d977  pop
0x6d978  rethrow
0x6d97a  ldarg.0
0x6d97b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6d980  ldc.i4.1
0x6d981  ldarg.0
0x6d982  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6d987  ldstr    aMonitoredexcha_3// "MonitoredExchangeService.SyncFolderHier"...
0x6d98c  ldarga.s 4
0x6d98e  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6d994  callvirt instance string [mscorlib]System.Object::ToString()
0x6d999  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6d99e  endfinally
0x6d99f  ldloc.0
0x6d9a0  ret
```
