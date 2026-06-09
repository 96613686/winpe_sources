# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::Initialize

- ea: `0x57640`
- end: `0x577dd`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::Initialize`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x57640`
- `0x57850`
- `0x578d0`
- `0x57a40`

## string_xrefs

- `0x576f5`: `IPM.Task`
- `0x577c3`: `IPM.Task`

## pseudocode

```c

```

## disassembly

```asm
0x57640  ldarg.0
0x57641  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::_lastFolderHierarchySyncStates
0x57646  call     T0x2B000099
0x5764b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::GetEnumerator()
0x57650  stloc.0
0x57651  br.s     loc_57662
0x57653  ldloca.s 0
0x57655  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_Current()
0x5765a  stloc.1
0x5765b  ldarg.0
0x5765c  ldloc.1
0x5765d  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::AddLastFolderHierarchySyncState(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState folderHierarchySyncState)
0x57662  ldloca.s 0
0x57664  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::MoveNext()
0x57669  brtrue.s loc_57653
0x5766b  leave.s  loc_5767B
0x5766d  ldloca.s 0
0x5766f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>
0x57675  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5767a  endfinally
0x5767b  ldarg.0
0x5767c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::_lastFolderHierarchySyncStatesIndexById
0x57681  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::ContactFolder
0x57686  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::ContainsKey(var<u1>)
0x5768b  brtrue.s loc_576AC
0x5768d  ldarg.0
0x5768e  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::ContactFolder
0x57693  ldstr    aIpmContact// "IPM.Contact"
0x57698  ldstr    aContact// "Contact"
0x5769d  ldsfld   string [mscorlib]System.String::Empty
0x576a2  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState::.ctor(string folderId, string folderClass, string folderName, string syncState)
0x576a7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::AddLastFolderHierarchySyncState(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState folderHierarchySyncState)
0x576ac  ldarg.0
0x576ad  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::_lastFolderHierarchySyncStatesIndexById
0x576b2  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::CalendarFolder
0x576b7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::ContainsKey(var<u1>)
0x576bc  brtrue.s loc_576DD
0x576be  ldarg.0
0x576bf  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::CalendarFolder
0x576c4  ldstr    aIpmAppointment// "IPM.Appointment"
0x576c9  ldstr    aAppointment// "Appointment"
0x576ce  ldsfld   string [mscorlib]System.String::Empty
0x576d3  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState::.ctor(string folderId, string folderClass, string folderName, string syncState)
0x576d8  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::AddLastFolderHierarchySyncState(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState folderHierarchySyncState)
0x576dd  ldarg.0
0x576de  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::_lastFolderHierarchySyncStatesIndexById
0x576e3  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::TaskFolder
0x576e8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::ContainsKey(var<u1>)
0x576ed  brtrue.s loc_5770E
0x576ef  ldarg.0
0x576f0  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::TaskFolder
0x576f5  ldstr    aIpmTask// "IPM.Task"
0x576fa  ldstr    aTask// "Task"
0x576ff  ldsfld   string [mscorlib]System.String::Empty
0x57704  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState::.ctor(string folderId, string folderClass, string folderName, string syncState)
0x57709  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::AddLastFolderHierarchySyncState(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState folderHierarchySyncState)
0x5770e  ldarg.0
0x5770f  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::_lastFolderItemsSyncStates
0x57714  call     T0x2B000099
0x57719  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::GetEnumerator()
0x5771e  stloc.0
0x5771f  br.s     loc_57730
0x57721  ldloca.s 0
0x57723  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::get_Current()
0x57728  stloc.2
0x57729  ldarg.0
0x5772a  ldloc.2
0x5772b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::AddLastFolderItemsSyncState(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState folderItemsSyncState)
0x57730  ldloca.s 0
0x57732  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::MoveNext()
0x57737  brtrue.s loc_57721
0x57739  leave.s  loc_57749
0x5773b  ldloca.s 0
0x5773d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>
0x57743  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57748  endfinally
0x57749  ldarg.0
0x5774a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::_lastFolderItemsSyncStatesIndexById
0x5774f  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::ContactFolder
0x57754  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::ContainsKey(var<u1>)
0x57759  brtrue.s loc_5777A
0x5775b  ldarg.0
0x5775c  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::ContactFolder
0x57761  ldstr    aIpmContact// "IPM.Contact"
0x57766  ldstr    aContact// "Contact"
0x5776b  ldsfld   string [mscorlib]System.String::Empty
0x57770  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState::.ctor(string folderId, string folderClass, string folderName, string syncState)
0x57775  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::AddLastFolderItemsSyncState(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState folderItemsSyncState)
0x5777a  ldarg.0
0x5777b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::_lastFolderItemsSyncStatesIndexById
0x57780  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::CalendarFolder
0x57785  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::ContainsKey(var<u1>)
0x5778a  brtrue.s loc_577AB
0x5778c  ldarg.0
0x5778d  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::CalendarFolder
0x57792  ldstr    aIpmAppointment// "IPM.Appointment"
0x57797  ldstr    aAppointment// "Appointment"
0x5779c  ldsfld   string [mscorlib]System.String::Empty
0x577a1  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState::.ctor(string folderId, string folderClass, string folderName, string syncState)
0x577a6  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::AddLastFolderItemsSyncState(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState folderItemsSyncState)
0x577ab  ldarg.0
0x577ac  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::_lastFolderItemsSyncStatesIndexById
0x577b1  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::TaskFolder
0x577b6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState>::ContainsKey(var<u1>)
0x577bb  brtrue.s loc_577DC
0x577bd  ldarg.0
0x577be  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::TaskFolder
0x577c3  ldstr    aIpmTask// "IPM.Task"
0x577c8  ldstr    aTask// "Task"
0x577cd  ldsfld   string [mscorlib]System.String::Empty
0x577d2  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState::.ctor(string folderId, string folderClass, string folderName, string syncState)
0x577d7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncState::AddLastFolderItemsSyncState(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeFolderSyncState folderItemsSyncState)
0x577dc  ret
```
