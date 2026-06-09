# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::CommitChanges

- ea: `0x5e410`
- end: `0x5e490`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::CommitChanges`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x57430`
- `0x57470`
- `0x57aa0`
- `0x57c00`
- `0x58c10`
- `0x5e4b0`
- `0x5e520`
- `0x5e6f0`
- `0x5ea80`

## string_xrefs

- `0x5e417`: `CommitChanges`
- `0x5e47b`: `CommitChanges`

## pseudocode

```c

```

## disassembly

```asm
0x5e410  ldc.i4.0
0x5e411  ldarg.0
0x5e412  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5e417  ldstr    aCommitchanges// "CommitChanges"
0x5e41c  ldstr    asc_8A7C2// ""
0x5e421  ldstr    asc_8A7C2// ""
0x5e426  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5e42b  ldarg.0
0x5e42c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_syncStateService
0x5e431  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::get_SyncState()
0x5e436  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x5e43b  stloc.0
0x5e43c  ldloca.s 0
0x5e43e  call     instance string [mscorlib]System.DateTime::ToString()
0x5e443  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::set_LastSyncEndTime(string value)
0x5e448  ldarg.0
0x5e449  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_syncStateService
0x5e44e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::get_SyncState()
0x5e453  ldarg.0
0x5e454  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ISyncDataProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_SyncDataProvider()
0x5e459  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.ISyncDataProvider::get_ChangesCount()
0x5e45e  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::set_LastSyncDataProviderChangeCount(int32 value)
0x5e463  ldarg.0
0x5e464  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_syncStateService
0x5e469  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::CommitSyncState()
0x5e46e  ldarg.0
0x5e46f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::ReportItemChanges()
0x5e474  ldc.i4.1
0x5e475  ldarg.0
0x5e476  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5e47b  ldstr    aCommitchanges// "CommitChanges"
0x5e480  ldstr    asc_8A7C2// ""
0x5e485  ldstr    asc_8A7C2// ""
0x5e48a  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5e48f  ret
```
