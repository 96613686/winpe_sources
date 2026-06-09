# Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::DeleteRestorePointAndLocations

- ea: `0x3c230`
- end: `0x3c38a`
- name: `Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::DeleteRestorePointAndLocations`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3bd70`

## callees

- `0x3c230`

## string_xrefs

- `0x3c2a6`: `DeleteRestorePointAndLocations`
- `0x3c31f`: `DeleteRestorePointAndLocations`
- `0x3c2c9`: `RestorePoint entity deleted`
- `0x3c343`: `RestorePoint location entities deleted`

## pseudocode

```c

```

## disassembly

```asm
0x3c230  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3c235  ldc.i4.s 0x1D
0x3c237  ldstr    aDeletingRestor// "Deleting RestorePoint: RestorePointId ="...
0x3c23c  ldc.i4.1
0x3c23d  newarr   [mscorlib]System.Object
0x3c242  dup
0x3c243  ldc.i4.0
0x3c244  ldarg.0
0x3c245  box      [mscorlib]System.Guid
0x3c24a  stelem.ref
0x3c24b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c250  ldarg.0
0x3c251  ldstr    aRestorepointid// "restorePointId"
0x3c256  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3c25b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x3c260  stloc.0
0x3c261  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3c266  ldc.i4.s 0x1D
0x3c268  ldstr    a0// "{0}"
0x3c26d  ldc.i4.1
0x3c26e  newarr   [mscorlib]System.Object
0x3c273  dup
0x3c274  ldc.i4.0
0x3c275  ldstr    aDeletingRestor_0// "Deleting RestorePoint entity"
0x3c27a  stelem.ref
0x3c27b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c280  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3c285  ldstr    aId// "Id"
0x3c28a  ldarg.0
0x3c28b  box      [mscorlib]System.Guid
0x3c290  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3c295  ldloc.0
0x3c296  ldstr    aRestorepoint// "RestorePoint"
0x3c29b  ldarg.0
0x3c29c  box      [mscorlib]System.Guid
0x3c2a1  ldc.i4   0x21F
0x3c2a6  ldstr    aDeleterestorep// "DeleteRestorePointAndLocations"
0x3c2ab  ldstr    aDA1SSrcCrmlive_66// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Resto"...
0x3c2b0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string, object, int32, string, string)
0x3c2b5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3c2ba  ldc.i4.s 0x1D
0x3c2bc  ldstr    a0// "{0}"
0x3c2c1  ldc.i4.1
0x3c2c2  newarr   [mscorlib]System.Object
0x3c2c7  dup
0x3c2c8  ldc.i4.0
0x3c2c9  ldstr    aRestorepointEn_2// "RestorePoint entity deleted"
0x3c2ce  stelem.ref
0x3c2cf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c2d4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3c2d9  ldc.i4.s 0x1D
0x3c2db  ldstr    a0// "{0}"
0x3c2e0  ldc.i4.1
0x3c2e1  newarr   [mscorlib]System.Object
0x3c2e6  dup
0x3c2e7  ldc.i4.0
0x3c2e8  ldstr    aDeletingRestor_1// "Deleting RestorePoint location entities"
0x3c2ed  stelem.ref
0x3c2ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c2f3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3c2f8  stloc.1
0x3c2f9  ldloc.1
0x3c2fa  ldstr    aRestorepointid_0// "RestorePointId"
0x3c2ff  ldarg.0
0x3c300  box      [mscorlib]System.Guid
0x3c305  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3c30a  ldloc.0
0x3c30b  ldstr    aRestorepointlo// "RestorePointLocation"
0x3c310  ldc.i4.1
0x3c311  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x3c316  dup
0x3c317  ldc.i4.0
0x3c318  ldloc.1
0x3c319  stelem.ref
0x3c31a  ldc.i4   0x228
0x3c31f  ldstr    aDeleterestorep// "DeleteRestorePointAndLocations"
0x3c324  ldstr    aDA1SSrcCrmlive_66// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Resto"...
0x3c329  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3c32e  pop
0x3c32f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3c334  ldc.i4.s 0x1D
0x3c336  ldstr    a0// "{0}"
0x3c33b  ldc.i4.1
0x3c33c  newarr   [mscorlib]System.Object
0x3c341  dup
0x3c342  ldc.i4.0
0x3c343  ldstr    aRestorepointLo_2// "RestorePoint location entities deleted"
0x3c348  stelem.ref
0x3c349  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c34e  leave.s  loc_3C35A
0x3c350  ldloc.0
0x3c351  brfalse.s loc_3C359
0x3c353  ldloc.0
0x3c354  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3c359  endfinally
0x3c35a  leave.s  loc_3C389
0x3c35c  stloc.2
0x3c35d  ldloc.2
0x3c35e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3c363  ldc.i4.s 0x1D
0x3c365  ldstr    aExceptionThrow_7// "Exception thrown while deleting Restore"...
0x3c36a  ldc.i4.2
0x3c36b  newarr   [mscorlib]System.Object
0x3c370  dup
0x3c371  ldc.i4.0
0x3c372  ldloc.2
0x3c373  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3c378  stelem.ref
0x3c379  dup
0x3c37a  ldc.i4.1
0x3c37b  ldloc.2
0x3c37c  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x3c381  stelem.ref
0x3c382  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3c387  rethrow
0x3c389  ret
```
