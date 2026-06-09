# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.SyncFolderHierarchyStep::ProcessResponse

- ea: `0x7f130`
- end: `0x7f2b1`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.SyncFolderHierarchyStep::ProcessResponse`
- size: `385`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x578d0`
- `0x57910`
- `0x579b0`
- `0x57a20`
- `0x57a40`
- `0x57aa0`
- `0x5a980`
- `0x7f130`

## string_xrefs

- `0x7f1a2`: `Synced the newly created folder "{0}" (items in this folder will be synced) from the exchange server for the mailbox : {1}.`
- `0x7f1ea`: `Synced the deleted folder "{0}" (items in this folder will not be synced) from the exchange server for the mailbox : {1}.`
- `0x7f22d`: `Synced the updated folder "{0}" from the exchange server for the mailbox : {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x7f130  ldarg.0
0x7f131  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>>::get_StepContext()
0x7f136  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_SyncStateService()
0x7f13b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::get_SyncState()
0x7f140  stloc.0
0x7f141  ldarg.0
0x7f142  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_Current()
0x7f147  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState::get_FolderId()
0x7f14c  pop
0x7f14d  ldarg.0
0x7f14e  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>>::get_Result()
0x7f153  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>::GetEnumerator()
0x7f158  stloc.1
0x7f159  br       loc_7F254
0x7f15e  ldloc.1
0x7f15f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>::get_Current()
0x7f164  stloc.2
0x7f165  ldloc.2
0x7f166  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeType [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Change::get_ChangeType()
0x7f16b  brtrue.s loc_7F1CE
0x7f16d  ldloc.2
0x7f16e  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange::get_FolderId()
0x7f173  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceId::get_UniqueId()
0x7f178  ldloc.2
0x7f179  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange::get_Folder()
0x7f17e  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::get_FolderClass()
0x7f183  ldloc.2
0x7f184  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange::get_Folder()
0x7f189  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::get_DisplayName()
0x7f18e  ldsfld   string [mscorlib]System.String::Empty
0x7f193  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState::.ctor(string folderId, string folderClass, string folderName, string syncState)
0x7f198  stloc.3
0x7f199  ldloc.0
0x7f19a  ldloc.3
0x7f19b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::AddLastFolderItemsSyncState(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState folderItemsSyncState)
0x7f1a0  ldarg.0
0x7f1a1  ldc.i4.4
0x7f1a2  ldstr    aSyncedTheNewly// "Synced the newly created folder \"{0}\""...
0x7f1a7  ldc.i4.2
0x7f1a8  newarr   [mscorlib]System.Object
0x7f1ad  dup
0x7f1ae  ldc.i4.0
0x7f1af  ldloc.2
0x7f1b0  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange::get_Folder()
0x7f1b5  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::get_DisplayName()
0x7f1ba  stelem.ref
0x7f1bb  dup
0x7f1bc  ldc.i4.1
0x7f1bd  ldarg.0
0x7f1be  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_MailboxId()
0x7f1c3  stelem.ref
0x7f1c4  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7f1c9  br       loc_7F254
0x7f1ce  ldloc.2
0x7f1cf  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeType [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Change::get_ChangeType()
0x7f1d4  ldc.i4.2
0x7f1d5  bne.un.s loc_7F222
0x7f1d7  ldloc.0
0x7f1d8  ldloc.2
0x7f1d9  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange::get_FolderId()
0x7f1de  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceId::get_UniqueId()
0x7f1e3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::RemoveLastFolderItemsSyncState(string folderId)
0x7f1e8  ldarg.0
0x7f1e9  ldc.i4.4
0x7f1ea  ldstr    aSyncedTheDelet// "Synced the deleted folder \"{0}\" (item"...
0x7f1ef  ldc.i4.2
0x7f1f0  newarr   [mscorlib]System.Object
0x7f1f5  dup
0x7f1f6  ldc.i4.0
0x7f1f7  ldloc.2
0x7f1f8  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange::get_Folder()
0x7f1fd  brtrue.s loc_7F206
0x7f1ff  ldsfld   string [mscorlib]System.String::Empty
0x7f204  br.s     loc_7F211
0x7f206  ldloc.2
0x7f207  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange::get_Folder()
0x7f20c  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::get_DisplayName()
0x7f211  stelem.ref
0x7f212  dup
0x7f213  ldc.i4.1
0x7f214  ldarg.0
0x7f215  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_MailboxId()
0x7f21a  stelem.ref
0x7f21b  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7f220  br.s     loc_7F254
0x7f222  ldloc.2
0x7f223  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeType [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Change::get_ChangeType()
0x7f228  ldc.i4.1
0x7f229  bne.un.s loc_7F254
0x7f22b  ldarg.0
0x7f22c  ldc.i4.4
0x7f22d  ldstr    aSyncedTheUpdat// "Synced the updated folder \"{0}\" from "...
0x7f232  ldc.i4.2
0x7f233  newarr   [mscorlib]System.Object
0x7f238  dup
0x7f239  ldc.i4.0
0x7f23a  ldloc.2
0x7f23b  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange::get_Folder()
0x7f240  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Folder::get_DisplayName()
0x7f245  stelem.ref
0x7f246  dup
0x7f247  ldc.i4.1
0x7f248  ldarg.0
0x7f249  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_MailboxId()
0x7f24e  stelem.ref
0x7f24f  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7f254  ldloc.1
0x7f255  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7f25a  brtrue   loc_7F15E
0x7f25f  leave.s  loc_7F26B
0x7f261  ldloc.1
0x7f262  brfalse.s loc_7F26A
0x7f264  ldloc.1
0x7f265  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f26a  endfinally
0x7f26b  ldarg.0
0x7f26c  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_Current()
0x7f271  ldarg.0
0x7f272  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>>::get_Result()
0x7f277  callvirt instance string class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>::get_SyncState()
0x7f27c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState::set_SyncState(string value)
0x7f281  ldarg.0
0x7f282  ldc.i4.4
0x7f283  ldstr    aSyncedTheFolde// "Synced the folder hierarchy of the fold"...
0x7f288  ldc.i4.2
0x7f289  newarr   [mscorlib]System.Object
0x7f28e  dup
0x7f28f  ldc.i4.0
0x7f290  ldarg.0
0x7f291  ldfld    class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.SyncFolderHierarchyStep::folderId
0x7f296  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderId::get_FolderName()
0x7f29b  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.WellKnownFolderName>
0x7f2a0  stelem.ref
0x7f2a1  dup
0x7f2a2  ldc.i4.1
0x7f2a3  ldarg.0
0x7f2a4  call     instance string class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncAsyncRemoteStep`2<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_MailboxId()
0x7f2a9  stelem.ref
0x7f2aa  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncSteps.ExchangeSyncStep`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ChangeCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.FolderChange>>::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7f2af  ldc.i4.1
0x7f2b0  ret
```
