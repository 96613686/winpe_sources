# Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::UnlinkRestorePoint

- ea: `0x3c390`
- end: `0x3c4e3`
- name: `Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::UnlinkRestorePoint`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x3bd70`

## callees

- `0x3c390`

## string_xrefs

- `0x3c397`: `Unlinking RestorePoint: RestorePointId = {0}`
- `0x3c3fd`: `UnlinkRestorePoint`
- `0x3c45a`: `UnlinkRestorePoint`
- `0x3c48a`: `Unlinked RestorePoint: RestorePointId = {0}`
- `0x3c4bc`: `Exception thrown while unlinking RestorePoint: Message = {0}, Stack Trace = {1}`

## pseudocode

```c

```

## disassembly

```asm
0x3c390  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3c395  ldc.i4.s 0x1D
0x3c397  ldstr    aUnlinkingResto// "Unlinking RestorePoint: RestorePointId "...
0x3c39c  ldc.i4.1
0x3c39d  newarr   [mscorlib]System.Object
0x3c3a2  dup
0x3c3a3  ldc.i4.0
0x3c3a4  ldarg.0
0x3c3a5  box      [mscorlib]System.Guid
0x3c3aa  stelem.ref
0x3c3ab  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c3b0  ldarg.0
0x3c3b1  ldstr    aRestorepointid// "restorePointId"
0x3c3b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3c3bb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x3c3c0  stloc.0
0x3c3c1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3c3c6  stloc.1
0x3c3c7  ldloc.1
0x3c3c8  ldstr    aUserrestorepoi// "UserRestorePointId"
0x3c3cd  ldarg.0
0x3c3ce  box      [mscorlib]System.Guid
0x3c3d3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3c3d8  ldc.i4.1
0x3c3d9  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x3c3de  dup
0x3c3df  ldc.i4.0
0x3c3e0  ldloc.1
0x3c3e1  stelem.ref
0x3c3e2  stloc.2
0x3c3e3  ldloc.0
0x3c3e4  ldstr    aRestorepoint// "RestorePoint"
0x3c3e9  ldc.i4.1
0x3c3ea  newarr   [mscorlib]System.String
0x3c3ef  dup
0x3c3f0  ldc.i4.0
0x3c3f1  ldstr    aId// "Id"
0x3c3f6  stelem.ref
0x3c3f7  ldloc.2
0x3c3f8  ldc.i4   0x247
0x3c3fd  ldstr    aUnlinkrestorep// "UnlinkRestorePoint"
0x3c402  ldstr    aDA1SSrcCrmlive_66// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Resto"...
0x3c407  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3c40c  stloc.3
0x3c40d  ldloc.3
0x3c40e  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x3c413  brtrue.s loc_3C483
0x3c415  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3c41a  stloc.s  4
0x3c41c  ldloc.s  4
0x3c41e  ldstr    aUserrestorepoi// "UserRestorePointId"
0x3c423  ldnull
0x3c424  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3c429  ldloc.3
0x3c42a  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x3c42f  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x3c434  stloc.s  5
0x3c436  br.s     loc_3C46A
0x3c438  ldloca.s 5
0x3c43a  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x3c43f  stloc.s  6
0x3c441  ldloc.0
0x3c442  ldstr    aRestorepoint// "RestorePoint"
0x3c447  ldloc.s  6
0x3c449  ldstr    aId// "Id"
0x3c44e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3c453  ldloc.s  4
0x3c455  ldc.i4   0x250
0x3c45a  ldstr    aUnlinkrestorep// "UnlinkRestorePoint"
0x3c45f  ldstr    aDA1SSrcCrmlive_66// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Resto"...
0x3c464  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x3c469  pop
0x3c46a  ldloca.s 5
0x3c46c  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x3c471  brtrue.s loc_3C438
0x3c473  leave.s  loc_3C483
0x3c475  ldloca.s 5
0x3c477  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x3c47d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3c482  endfinally
0x3c483  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3c488  ldc.i4.s 0x1D
0x3c48a  ldstr    aUnlinkedRestor// "Unlinked RestorePoint: RestorePointId ="...
0x3c48f  ldc.i4.1
0x3c490  newarr   [mscorlib]System.Object
0x3c495  dup
0x3c496  ldc.i4.0
0x3c497  ldarg.0
0x3c498  box      [mscorlib]System.Guid
0x3c49d  stelem.ref
0x3c49e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c4a3  leave.s  loc_3C4AF
0x3c4a5  ldloc.0
0x3c4a6  brfalse.s loc_3C4AE
0x3c4a8  ldloc.0
0x3c4a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3c4ae  endfinally
0x3c4af  leave.s  loc_3C4E2
0x3c4b1  stloc.s  7
0x3c4b3  ldloc.s  7
0x3c4b5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3c4ba  ldc.i4.s 0x1D
0x3c4bc  ldstr    aExceptionThrow_8// "Exception thrown while unlinking Restor"...
0x3c4c1  ldc.i4.2
0x3c4c2  newarr   [mscorlib]System.Object
0x3c4c7  dup
0x3c4c8  ldc.i4.0
0x3c4c9  ldloc.s  7
0x3c4cb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3c4d0  stelem.ref
0x3c4d1  dup
0x3c4d2  ldc.i4.1
0x3c4d3  ldloc.s  7
0x3c4d5  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x3c4da  stelem.ref
0x3c4db  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c4e0  rethrow
0x3c4e2  ret
```
