# Microsoft.Crm.Admin.AdminService.ImportOrganizationManifestAction::CreateOrUpdateRow

- ea: `0x2d2f0`
- end: `0x2d421`
- name: `Microsoft.Crm.Admin.AdminService.ImportOrganizationManifestAction::CreateOrUpdateRow`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x2ce70`

## callees

- `0x2cd40`
- `0x2d2f0`
- `0x2d5e0`

## string_xrefs

- `0x2d31e`: `D:\a\1\s\src\CrmLive\Admin\Organization\ImportOrganizationManifestAction.cs`
- `0x2d33a`: `D:\a\1\s\src\CrmLive\Admin\Organization\ImportOrganizationManifestAction.cs`
- `0x2d384`: `D:\a\1\s\src\CrmLive\Admin\Organization\ImportOrganizationManifestAction.cs`
- `0x2d39b`: `D:\a\1\s\src\CrmLive\Admin\Organization\ImportOrganizationManifestAction.cs`
- `0x2d3dc`: `D:\a\1\s\src\CrmLive\Admin\Organization\ImportOrganizationManifestAction.cs`
- `0x2d319`: `CreateOrUpdateRow`
- `0x2d335`: `CreateOrUpdateRow`
- `0x2d37f`: `CreateOrUpdateRow`
- `0x2d396`: `CreateOrUpdateRow`
- `0x2d3d7`: `CreateOrUpdateRow`

## pseudocode

```c

```

## disassembly

```asm
0x2d2f0  ldarg.s  5
0x2d2f2  brfalse.s loc_2D353
0x2d2f4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2d2f9  stloc.0
0x2d2fa  ldloc.0
0x2d2fb  ldstr    aId// "Id"
0x2d300  ldarg.s  4
0x2d302  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2d307  ldarg.1
0x2d308  ldarg.2
0x2d309  ldarg.3
0x2d30a  ldc.i4.1
0x2d30b  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x2d310  dup
0x2d311  ldc.i4.0
0x2d312  ldloc.0
0x2d313  stelem.ref
0x2d314  ldc.i4   0xF6
0x2d319  ldstr    aCreateorupdate// "CreateOrUpdateRow"
0x2d31e  ldstr    aDA1SSrcCrmlive_54// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2d323  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x2d328  brtrue   loc_2D3F0
0x2d32d  ldarg.1
0x2d32e  ldarg.2
0x2d32f  ldarg.3
0x2d330  ldc.i4   0xFA
0x2d335  ldstr    aCreateorupdate// "CreateOrUpdateRow"
0x2d33a  ldstr    aDA1SSrcCrmlive_54// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2d33f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2d344  pop
0x2d345  ldarg.0
0x2d346  ldarg.2
0x2d347  ldarg.s  4
0x2d349  call     instance void Microsoft.Crm.Admin.AdminService.ImportOrganizationManifestAction::AddToHistory(string table, object pk)
0x2d34e  br       loc_2D3F0
0x2d353  ldarg.0
0x2d354  call     instance bool Microsoft.Crm.Admin.AdminService.ImportOrganizationManifestAction::get_ImportingOverExistingOrgLc()
0x2d359  brfalse.s loc_2D3CF
0x2d35b  ldarg.2
0x2d35c  ldstr    aOrganizationli// "OrganizationLifecycle"
0x2d361  ldc.i4.5
0x2d362  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2d367  brtrue.s loc_2D3CF
0x2d369  ldarg.1
0x2d36a  ldc.i4.2
0x2d36b  ldc.i4   0x1000
0x2d370  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::BeginTransaction(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope, valuetype [System.Data]System.Data.IsolationLevel)
0x2d375  stloc.1
0x2d376  ldarg.1
0x2d377  ldarg.2
0x2d378  ldarg.s  4
0x2d37a  ldc.i4   0x104
0x2d37f  ldstr    aCreateorupdate// "CreateOrUpdateRow"
0x2d384  ldstr    aDA1SSrcCrmlive_54// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2d389  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x2d38e  ldarg.1
0x2d38f  ldarg.2
0x2d390  ldarg.3
0x2d391  ldc.i4   0x105
0x2d396  ldstr    aCreateorupdate// "CreateOrUpdateRow"
0x2d39b  ldstr    aDA1SSrcCrmlive_54// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2d3a0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2d3a5  pop
0x2d3a6  ldloc.1
0x2d3a7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction::CommitTransaction()
0x2d3ac  leave.s  loc_2D3B8
0x2d3ae  pop
0x2d3af  ldloc.1
0x2d3b0  ldc.i4.0
0x2d3b1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction::RollbackTransaction(bool)
0x2d3b6  rethrow
0x2d3b8  leave.s  loc_2D3C4
0x2d3ba  ldloc.1
0x2d3bb  brfalse.s loc_2D3C3
0x2d3bd  ldloc.1
0x2d3be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d3c3  endfinally
0x2d3c4  ldarg.0
0x2d3c5  ldarg.2
0x2d3c6  ldarg.s  4
0x2d3c8  call     instance void Microsoft.Crm.Admin.AdminService.ImportOrganizationManifestAction::AddToHistory(string table, object pk)
0x2d3cd  br.s     loc_2D3F0
0x2d3cf  ldarg.1
0x2d3d0  ldarg.2
0x2d3d1  ldarg.3
0x2d3d2  ldc.i4   0x112
0x2d3d7  ldstr    aCreateorupdate// "CreateOrUpdateRow"
0x2d3dc  ldstr    aDA1SSrcCrmlive_54// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2d3e1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2d3e6  pop
0x2d3e7  ldarg.0
0x2d3e8  ldarg.2
0x2d3e9  ldarg.s  4
0x2d3eb  call     instance void Microsoft.Crm.Admin.AdminService.ImportOrganizationManifestAction::AddToHistory(string table, object pk)
0x2d3f0  leave.s  loc_2D420
0x2d3f2  stloc.2
0x2d3f3  ldarg.2
0x2d3f4  ldstr    aSystemuser// "SystemUser"
0x2d3f9  ldc.i4.5
0x2d3fa  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2d3ff  brfalse.s loc_2D40F
0x2d401  ldarg.2
0x2d402  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x2d407  ldc.i4.5
0x2d408  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2d40d  brtrue.s loc_2D41E
0x2d40f  ldloc.2
0x2d410  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x2d415  ldc.i4   0x80131904
0x2d41a  bne.un.s loc_2D41E
0x2d41c  leave.s  loc_2D420
0x2d41e  rethrow
0x2d420  ret
```
