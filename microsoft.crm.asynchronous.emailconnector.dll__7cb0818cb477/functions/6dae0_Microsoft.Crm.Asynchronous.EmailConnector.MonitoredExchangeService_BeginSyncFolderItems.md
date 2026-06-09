# Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::BeginSyncFolderItems

- ea: `0x6dae0`
- end: `0x6db63`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::BeginSyncFolderItems`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7f340`

## callees

- `0x58bb0`
- `0x6d670`
- `0x6d740`
- `0x6dae0`

## string_xrefs

- `0x6dae7`: `MonitoredExchangeService.BeginSyncFolderItems`
- `0x6db49`: `MonitoredExchangeService.BeginSyncFolderItems`

## pseudocode

```c

```

## disassembly

```asm
0x6dae0  ldc.i4.0
0x6dae1  ldarg.0
0x6dae2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6dae7  ldstr    aMonitoredexcha_7// "MonitoredExchangeService.BeginSyncFolde"...
0x6daec  ldarga.s 9
0x6daee  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6daf4  callvirt instance string [mscorlib]System.Object::ToString()
0x6daf9  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6dafe  ldarg.0
0x6daff  ldftn    instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::Callback(class [mscorlib]System.IAsyncResult asyncResult)
0x6db05  newobj   instance void [mscorlib]System.AsyncCallback::.ctor(object, native int)
0x6db0a  ldarg.1
0x6db0b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x6db10  castclass [mscorlib]System.AsyncCallback
0x6db15  stloc.1
0x6db16  ldarg.0
0x6db17  ldarg.s  9
0x6db19  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionOpened(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType exchangeItemType)
0x6db1e  ldarg.0
0x6db1f  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_exchangeService
0x6db24  ldloc.1
0x6db25  ldarg.2
0x6db26  ldarg.3
0x6db27  ldarg.s  4
0x6db29  ldarg.s  5
0x6db2b  ldarg.s  6
0x6db2d  ldarg.s  7
0x6db2f  ldarg.s  8
0x6db31  callvirt instance class [mscorlib]System.IAsyncResult [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService::BeginSyncFolderItems(class [mscorlib]System.AsyncCallback, object, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.PropertySet, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId>, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.SyncFolderItemsScope, string)
0x6db36  stloc.0
0x6db37  leave.s  loc_6DB61
0x6db39  pop
0x6db3a  ldarg.0
0x6db3b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::RegisterConnectionClosed()
0x6db40  rethrow
0x6db42  ldc.i4.1
0x6db43  ldarg.0
0x6db44  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.MonitoredExchangeService::_context
0x6db49  ldstr    aMonitoredexcha_7// "MonitoredExchangeService.BeginSyncFolde"...
0x6db4e  ldarga.s 9
0x6db50  constrained. Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType
0x6db56  callvirt instance string [mscorlib]System.Object::ToString()
0x6db5b  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteExchangeServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string itemType)
0x6db60  endfinally
0x6db61  ldloc.0
0x6db62  ret
```
