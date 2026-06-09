# Microsoft.Crm.Authentication.UserManagementFactory::UpdateDirectoryObjectId

- ea: `0x113b0`
- end: `0x114aa`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::UpdateDirectoryObjectId`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x111d0`

## callees

- `0x113b0`

## string_xrefs

- `0x113ea`: `DirectoryObjectId`
- `0x11410`: `UpdateDirectoryObjectId`
- `0x1148d`: `UpdateDirectoryObjectId`
- `0x11477`: `DirectoryObjectState`

## pseudocode

```c

```

## disassembly

```asm
0x113b0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x113b5  stloc.0
0x113b6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x113bb  stloc.1
0x113bc  ldloc.1
0x113bd  ldstr    aCrmuserid// "CrmUserId"
0x113c2  ldarg.2
0x113c3  box      [mscorlib]System.Guid
0x113c8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x113cd  ldloc.1
0x113ce  ldstr    aOrganizationid_1// "OrganizationId"
0x113d3  ldarg.1
0x113d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x113d9  box      [mscorlib]System.Guid
0x113de  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x113e3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x113e8  stloc.2
0x113e9  ldloc.2
0x113ea  ldstr    aDirectoryobjec// "DirectoryObjectId"
0x113ef  ldarg.3
0x113f0  box      [mscorlib]System.Guid
0x113f5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x113fa  ldloc.0
0x113fb  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x11400  ldloc.2
0x11401  ldc.i4.1
0x11402  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x11407  dup
0x11408  ldc.i4.0
0x11409  ldloc.1
0x1140a  stelem.ref
0x1140b  ldc.i4   0x1BB
0x11410  ldstr    aUpdatedirector// "UpdateDirectoryObjectId"
0x11415  ldstr    aDA1SSrcManaged_1// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x1141a  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1141f  pop
0x11420  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x11425  stloc.3
0x11426  ldloc.3
0x11427  ldstr    aObjectid_0// "ObjectId"
0x1142c  ldarg.3
0x1142d  box      [mscorlib]System.Guid
0x11432  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11437  call     T0x2B00002A
0x1143c  stloc.s  4
0x1143e  ldloc.s  4
0x11440  brfalse.s loc_1145D
0x11442  ldloc.s  4
0x11444  ldarg.1
0x11445  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1144a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProviderFactory::GetProvider(valuetype [mscorlib]System.Guid)
0x1144f  ldarg.1
0x11450  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11455  ldarg.3
0x11456  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::SetIsToBeAppliedForOrganizationByObjectId(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1145b  leave.s  loc_114A9
0x1145d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x11462  stloc.s  5
0x11464  ldloc.s  5
0x11466  ldstr    aIstobeapplied// "IsToBeApplied"
0x1146b  ldc.i4.1
0x1146c  box      [mscorlib]System.Boolean
0x11471  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x11476  ldloc.0
0x11477  ldstr    aDirectoryobjec_0// "DirectoryObjectState"
0x1147c  ldloc.s  5
0x1147e  ldc.i4.1
0x1147f  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x11484  dup
0x11485  ldc.i4.0
0x11486  ldloc.3
0x11487  stelem.ref
0x11488  ldc.i4   0x1CC
0x1148d  ldstr    aUpdatedirector// "UpdateDirectoryObjectId"
0x11492  ldstr    aDA1SSrcManaged_1// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x11497  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1149c  pop
0x1149d  leave.s  loc_114A9
0x1149f  ldloc.0
0x114a0  brfalse.s loc_114A8
0x114a2  ldloc.0
0x114a3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x114a8  endfinally
0x114a9  ret
```
