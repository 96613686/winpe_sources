# Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::CommitChanges

- ea: `0x5c5c0`
- end: `0x5c805`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::CommitChanges`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x417a0`
- `0x4d8c0`
- `0x4da80`
- `0x521e0`
- `0x52650`
- `0x528d0`
- `0x528f0`
- `0x52910`
- `0x52930`
- `0x52950`
- `0x52970`
- `0x52990`
- `0x529b0`
- `0x55c40`
- `0x57580`
- `0x57aa0`
- `0x58c10`
- `0x59000`
- `0x5c5c0`
- `0x5e4b0`
- `0x5e4c0`
- `0x5e500`
- `0x5e6b0`
- `0x5e6f0`
- `0x62c10`
- `0x71c20`
- `0x71cf0`
- `0x829c0`

## string_xrefs

- `0x5c7ac`: `Server-Side Synchronization: Current Number of ACTs Have Not Synchronized From CRM Server`
- `0x5c5c7`: `CommitChanges`
- `0x5c7f0`: `CommitChanges`

## pseudocode

```c

```

## disassembly

```asm
0x5c5c0  ldc.i4.0
0x5c5c1  ldarg.0
0x5c5c2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5c5c7  ldstr    aCommitchanges// "CommitChanges"
0x5c5cc  ldstr    asc_8A7C2// ""
0x5c5d1  ldstr    asc_8A7C2// ""
0x5c5d6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5c5db  ldc.i4.0
0x5c5dc  stloc.0
0x5c5dd  ldarg.0
0x5c5de  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo> Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::_crmSyncInfoCollection
0x5c5e3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo>::GetEnumerator()
0x5c5e8  stloc.1
0x5c5e9  br       loc_5C795
0x5c5ee  ldloc.1
0x5c5ef  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo>::get_Current()
0x5c5f4  stloc.2
0x5c5f5  ldloc.2
0x5c5f6  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_EntityName()
0x5c5fb  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetExchangeItemType(string entityName)
0x5c600  stloc.3
0x5c601  ldloc.2
0x5c602  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualDeleteCount()
0x5c607  ldc.i4.0
0x5c608  bgt.s    loc_5C613
0x5c60a  ldloc.2
0x5c60b  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_IgnoredDeletesCount()
0x5c610  ldc.i4.0
0x5c611  ble.s    loc_5C654
0x5c613  ldarg.0
0x5c614  ldloc.3
0x5c615  ldloc.2
0x5c616  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualDeleteCount()
0x5c61b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::RecordReportedItemChanges(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType itemType, int32 changeCount)
0x5c620  ldarg.0
0x5c621  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_InputProvider()
0x5c626  castclass Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider
0x5c62b  ldarg.0
0x5c62c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_syncStateService
0x5c631  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::get_SyncState()
0x5c636  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_ClientId()
0x5c63b  ldloc.2
0x5c63c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_EntityName()
0x5c641  ldc.i4.2
0x5c642  ldloc.2
0x5c643  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualDeleteCount()
0x5c648  ldloc.2
0x5c649  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_IgnoredDeletesCount()
0x5c64e  add
0x5c64f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::PostSync(string clientId, string entityName, valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.SyncAction syncAction, int32 batchSize)
0x5c654  ldloc.2
0x5c655  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualInsertCount()
0x5c65a  ldc.i4.0
0x5c65b  ble.s    loc_5C697
0x5c65d  ldarg.0
0x5c65e  ldloc.3
0x5c65f  ldloc.2
0x5c660  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualInsertCount()
0x5c665  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::RecordReportedItemChanges(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType itemType, int32 changeCount)
0x5c66a  ldarg.0
0x5c66b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_InputProvider()
0x5c670  castclass Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider
0x5c675  ldarg.0
0x5c676  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_syncStateService
0x5c67b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::get_SyncState()
0x5c680  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_ClientId()
0x5c685  ldloc.2
0x5c686  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_EntityName()
0x5c68b  ldc.i4.1
0x5c68c  ldloc.2
0x5c68d  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualInsertCount()
0x5c692  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::PostSync(string clientId, string entityName, valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.SyncAction syncAction, int32 batchSize)
0x5c697  ldloc.2
0x5c698  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualUpdateCount()
0x5c69d  ldc.i4.0
0x5c69e  ble.s    loc_5C6EC
0x5c6a0  ldloc.2
0x5c6a1  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_EntityName()
0x5c6a6  ldstr    aAccount// "Account"
0x5c6ab  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5c6b0  brfalse.s loc_5C6EC
0x5c6b2  ldarg.0
0x5c6b3  ldloc.3
0x5c6b4  ldloc.2
0x5c6b5  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualUpdateCount()
0x5c6ba  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::RecordReportedItemChanges(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType itemType, int32 changeCount)
0x5c6bf  ldarg.0
0x5c6c0  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_InputProvider()
0x5c6c5  castclass Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider
0x5c6ca  ldarg.0
0x5c6cb  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_syncStateService
0x5c6d0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::get_SyncState()
0x5c6d5  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::get_ClientId()
0x5c6da  ldloc.2
0x5c6db  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_EntityName()
0x5c6e0  ldc.i4.3
0x5c6e1  ldloc.2
0x5c6e2  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualUpdateCount()
0x5c6e7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::PostSync(string clientId, string entityName, valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.SyncAction syncAction, int32 batchSize)
0x5c6ec  nop
0x5c6ed  ldloc.0
0x5c6ee  ldloc.2
0x5c6ef  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_DeleteCount()
0x5c6f4  ldloc.2
0x5c6f5  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualDeleteCount()
0x5c6fa  sub
0x5c6fb  ldloc.2
0x5c6fc  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_InsertCount()
0x5c701  ldloc.2
0x5c702  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualInsertCount()
0x5c707  sub
0x5c708  add
0x5c709  ldloc.2
0x5c70a  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_UpdateCount()
0x5c70f  ldloc.2
0x5c710  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::get_ActualUpdateCount()
0x5c715  sub
0x5c716  add
0x5c717  add
0x5c718  stloc.0
0x5c719  leave.s  loc_5C795
0x5c71b  stloc.s  4
0x5c71d  ldc.i4   0x7FFFFFFF
0x5c722  stloc.0
0x5c723  ldarg.0
0x5c724  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_exchangeSyncWorker
0x5c729  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x5c72e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox ACTState::get_InternalMailbox()
0x5c733  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x5c738  ldarg.0
0x5c739  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_exchangeSyncWorker
0x5c73e  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x5c743  ldarg.0
0x5c744  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_exchangeSyncWorker
0x5c749  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Context()
0x5c74e  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x5c753  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x5c758  ldc.i4.s 0x3D
0x5c75a  ldc.i4.1
0x5c75b  ldstr    aExchangesyncin// "ExchangeSyncingItems: Error Mailbox {0}"...
0x5c760  ldc.i4.2
0x5c761  newarr   [mscorlib]System.Object
0x5c766  dup
0x5c767  ldc.i4.0
0x5c768  ldarg.0
0x5c769  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5c76e  stelem.ref
0x5c76f  dup
0x5c770  ldc.i4.1
0x5c771  ldloc.s  4
0x5c773  ldarg.0
0x5c774  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_exchangeSyncWorker
0x5c779  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x5c77e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox ACTState::get_InternalMailbox()
0x5c783  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x5c788  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x5c78d  stelem.ref
0x5c78e  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5c793  leave.s  loc_5C795
0x5c795  ldloc.1
0x5c796  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5c79b  brtrue   loc_5C5EE
0x5c7a0  leave.s  loc_5C7AC
0x5c7a2  ldloc.1
0x5c7a3  brfalse.s loc_5C7AB
0x5c7a5  ldloc.1
0x5c7a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5c7ab  endfinally
0x5c7ac  ldstr    aServerSideSync_104// "Server-Side Synchronization: Current Nu"...
0x5c7b1  ldloc.0
0x5c7b2  conv.i8
0x5c7b3  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName, int64 increment)
0x5c7b8  ldarg.0
0x5c7b9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_exchangeSyncWorker
0x5c7be  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x5c7c3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox ACTState::get_InternalMailbox()
0x5c7c8  ldstr    aCrmitemsbacklo// "crmitemsbacklog"
0x5c7cd  ldloc.0
0x5c7ce  box      [mscorlib]System.Int32
0x5c7d3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_Item(string attributeName, object value)
0x5c7d8  ldarg.0
0x5c7d9  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo> Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::_crmSyncInfoCollection
0x5c7de  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo>::Clear()
0x5c7e3  ldarg.0
0x5c7e4  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::ReportItemChanges()
0x5c7e9  ldc.i4.1
0x5c7ea  ldarg.0
0x5c7eb  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5c7f0  ldstr    aCommitchanges// "CommitChanges"
0x5c7f5  ldstr    asc_8A7C2// ""
0x5c7fa  ldstr    asc_8A7C2// ""
0x5c7ff  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5c804  ret
```
