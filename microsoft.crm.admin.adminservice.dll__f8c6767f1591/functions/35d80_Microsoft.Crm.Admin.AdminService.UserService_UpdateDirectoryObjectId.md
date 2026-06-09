# Microsoft.Crm.Admin.AdminService.UserService::UpdateDirectoryObjectId

- ea: `0x35d80`
- end: `0x35e35`
- name: `Microsoft.Crm.Admin.AdminService.UserService::UpdateDirectoryObjectId`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x35a20`

## callees

- `0x35d80`
- `0x36020`
- `0x36470`

## string_xrefs

- `0x35dd4`: `DirectoryObjectState`
- `0x35def`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35dea`: `UpdateDirectoryObjectId`
- `0x35e0b`: `Exception occured while updating IsToBeApplied flag. OrganizationId: {0}, DirectoryObjectId: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x35d80  ldarg.2
0x35d81  ldc.i4.1
0x35d82  bne.un.s loc_35D85
0x35d84  ret
0x35d85  nop
0x35d86  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x35d8b  stloc.0
0x35d8c  call     T0x2B0000B2
0x35d91  stloc.1
0x35d92  ldloc.1
0x35d93  brfalse.s loc_35DA5
0x35d95  ldloc.1
0x35d96  ldarg.0
0x35d97  callvirt instance class Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProviderFactory::GetProvider(valuetype [mscorlib]System.Guid organizationId)
0x35d9c  ldarg.0
0x35d9d  ldarg.1
0x35d9e  callvirt instance void Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::SetIsToBeAppliedForOrganizationByObjectId(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid objectId)
0x35da3  br.s     loc_35DFA
0x35da5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x35daa  stloc.2
0x35dab  ldloc.2
0x35dac  ldstr    aObjectid_0// "ObjectId"
0x35db1  ldarg.1
0x35db2  box      [mscorlib]System.Guid
0x35db7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35dbc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x35dc1  stloc.3
0x35dc2  ldloc.3
0x35dc3  ldstr    aIstobeapplied// "IsToBeApplied"
0x35dc8  ldc.i4.1
0x35dc9  box      [mscorlib]System.Boolean
0x35dce  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35dd3  ldloc.0
0x35dd4  ldstr    aDirectoryobjec// "DirectoryObjectState"
0x35dd9  ldloc.3
0x35dda  ldc.i4.1
0x35ddb  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x35de0  dup
0x35de1  ldc.i4.0
0x35de2  ldloc.2
0x35de3  stelem.ref
0x35de4  ldc.i4.0
0x35de5  ldc.i4   0x26E
0x35dea  ldstr    aUpdatedirector// "UpdateDirectoryObjectId"
0x35def  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x35df4  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], bool, int32, string, string)
0x35df9  pop
0x35dfa  leave.s  loc_35E06
0x35dfc  ldloc.0
0x35dfd  brfalse.s loc_35E05
0x35dff  ldloc.0
0x35e00  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35e05  endfinally
0x35e06  leave.s  loc_35E34
0x35e08  ldarg.0
0x35e09  ldc.i4.s 0x48
0x35e0b  ldstr    aExceptionOccur// "Exception occured while updating IsToBe"...
0x35e10  ldarg.0
0x35e11  box      [mscorlib]System.Guid
0x35e16  ldarg.1
0x35e17  box      [mscorlib]System.Guid
0x35e1c  call     string [mscorlib]System.String::Format(string, object, object)
0x35e21  ldc.i4.0
0x35e22  newarr   [mscorlib]System.Object
0x35e27  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x35e2c  ldarg.2
0x35e2d  ldc.i4.2
0x35e2e  beq.s    loc_35E32
0x35e30  rethrow
0x35e32  leave.s  loc_35E34
0x35e34  ret
```
