# Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::Delete

- ea: `0x1cb80`
- end: `0x1cc20`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::Delete`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x22940`

## callees

- `0x1cad0`
- `0x1cb80`
- `0x1cd60`

## string_xrefs

- `0x1cbc6`: `Delete`
- `0x1cbf0`: `Delete`
- `0x1cbcb`: `D:\a\1\s\src\CrmLive\Admin\OrganizationGroup\CrmOrganizationGroupService.cs`
- `0x1cbf5`: `D:\a\1\s\src\CrmLive\Admin\OrganizationGroup\CrmOrganizationGroupService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x1cb80  ldarg.1
0x1cb81  ldstr    aGroupid_0// "groupId"
0x1cb86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1cb8b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1cb90  stloc.0
0x1cb91  ldloc.0
0x1cb92  ldc.i4.2
0x1cb93  ldc.i4   0x1000
0x1cb98  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::BeginTransaction(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope, valuetype [System.Data]System.Data.IsolationLevel)
0x1cb9d  stloc.1
0x1cb9e  ldarg.0
0x1cb9f  ldarg.1
0x1cba0  call     instance class Microsoft.Crm.Admin.AdminService.OrganizationGroupEntryData[] Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::GetOrganizationGroupEntriesForOrganizationGroup(valuetype [mscorlib]System.Guid groupId)
0x1cba5  stloc.2
0x1cba6  ldc.i4.0
0x1cba7  stloc.3
0x1cba8  br.s     loc_1CBD9
0x1cbaa  ldloc.2
0x1cbab  ldloc.3
0x1cbac  ldelem.ref
0x1cbad  stloc.s  4
0x1cbaf  ldloc.0
0x1cbb0  ldstr    aOrganizationgr_0// "OrganizationGroupOrganizations"
0x1cbb5  ldloc.s  4
0x1cbb7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationGroupEntryData::get_Id()
0x1cbbc  box      [mscorlib]System.Guid
0x1cbc1  ldc.i4   0x91
0x1cbc6  ldstr    aDelete// "Delete"
0x1cbcb  ldstr    aDA1SSrcCrmlive_39// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x1cbd0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x1cbd5  ldloc.3
0x1cbd6  ldc.i4.1
0x1cbd7  add
0x1cbd8  stloc.3
0x1cbd9  ldloc.3
0x1cbda  ldloc.2
0x1cbdb  ldlen
0x1cbdc  conv.i4
0x1cbdd  blt.s    loc_1CBAA
0x1cbdf  ldloc.0
0x1cbe0  ldstr    aOrganizationgr// "OrganizationGroup"
0x1cbe5  ldarg.1
0x1cbe6  box      [mscorlib]System.Guid
0x1cbeb  ldc.i4   0x94
0x1cbf0  ldstr    aDelete// "Delete"
0x1cbf5  ldstr    aDA1SSrcCrmlive_39// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x1cbfa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x1cbff  leave.s  loc_1CC1F
0x1cc01  pop
0x1cc02  ldloc.1
0x1cc03  ldc.i4.0
0x1cc04  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction::RollbackTransaction(bool)
0x1cc09  rethrow
0x1cc0b  ldloc.1
0x1cc0c  brfalse.s loc_1CC14
0x1cc0e  ldloc.1
0x1cc0f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cc14  endfinally
0x1cc15  ldloc.0
0x1cc16  brfalse.s loc_1CC1E
0x1cc18  ldloc.0
0x1cc19  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cc1e  endfinally
0x1cc1f  ret
```
