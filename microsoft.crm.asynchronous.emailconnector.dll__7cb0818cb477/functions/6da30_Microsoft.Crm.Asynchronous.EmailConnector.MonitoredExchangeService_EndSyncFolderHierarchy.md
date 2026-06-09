# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::EndSyncFolderHierarchy

- ea: `0x6da30`
- end: `0x6da6e`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::EndSyncFolderHierarchy`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x7f100`

## callees

- `0x58bb0`
- `0x6da30`

## string_xrefs

- `0x6da37`: `MonitoredExchangeService.EndSyncFolderHierarchy`
- `0x6da5c`: `MonitoredExchangeService.EndSyncFolderHierarchy`

## pseudocode

```c

```

## disassembly

```asm
0x6da30  ldc.i4.0
0x6da31  ldarg.0
0x6da32  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6da37  ldstr    aMonitoredexcha_5// "MonitoredExchangeService.EndSyncFolderH"...
0x6da3c  ldstr    aItem_0// "Item"
0x6da41  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6da46  ldarg.0
0x6da47  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6da4c  ldarg.1
0x6da4d  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::EndSyncFolderHierarchy(class [mscorlib]System.IAsyncResult)
0x6da52  stloc.0
0x6da53  leave.s  loc_6DA6C
0x6da55  ldc.i4.1
0x6da56  ldarg.0
0x6da57  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6da5c  ldstr    aMonitoredexcha_5// "MonitoredExchangeService.EndSyncFolderH"...
0x6da61  ldstr    aItem_0// "Item"
0x6da66  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6da6b  endfinally
0x6da6c  ldloc.0
0x6da6d  ret
```
