# Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::Do

- ea: `0x2d690`
- end: `0x2d84d`
- name: `Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::Do`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x163a0`

## callees

- `0x2be40`
- `0x2be90`
- `0x2bf10`
- `0x2d690`
- `0x2d850`
- `0x2d940`
- `0x2d980`
- `0x2da00`

## string_xrefs

- `0x2d7e9`: `ServiceInstance`
- `0x2d6ac`: `ConfigurationMetadata`
- `0x2d6fb`: `D:\a\1\s\src\CrmLive\Admin\Organization\ExportOrganizationManifestAction.cs`

## pseudocode

```c

```

## disassembly

```asm
0x2d690  ldnull
0x2d691  stloc.0
0x2d692  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2d697  stloc.s  5
0x2d699  ldloc.s  5
0x2d69b  ldc.i4.0
0x2d69c  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::NewConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x2d6a1  stloc.s  6
0x2d6a3  ldloc.s  6
0x2d6a5  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x2d6aa  ldloc.s  6
0x2d6ac  ldstr    aConfigurationm// "ConfigurationMetadata"
0x2d6b1  call     class [mscorlib]System.Version [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.SqlHelpers::GetCurrentVersion(class [System.Data]System.Data.IDbConnection, string)
0x2d6b6  stloc.0
0x2d6b7  leave.s  loc_2D6D1
0x2d6b9  ldloc.s  6
0x2d6bb  brfalse.s loc_2D6C4
0x2d6bd  ldloc.s  6
0x2d6bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d6c4  endfinally
0x2d6c5  ldloc.s  5
0x2d6c7  brfalse.s loc_2D6D0
0x2d6c9  ldloc.s  5
0x2d6cb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d6d0  endfinally
0x2d6d1  ldloc.0
0x2d6d2  ldnull
0x2d6d3  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2d6d8  brtrue.s loc_2D6E2
0x2d6da  ldloc.0
0x2d6db  callvirt instance string [mscorlib]System.Object::ToString()
0x2d6e0  br.s     loc_2D6E3
0x2d6e2  ldnull
0x2d6e3  call     class Microsoft.Crm.Admin.AdminService.IOrganizationManifest Microsoft.Crm.Admin.AdminService.OrganizationManifestFactory::CreateEmpty(string dbVersion)
0x2d6e8  stloc.1
0x2d6e9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x2d6ee  ldarg.0
0x2d6ef  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::_organizationId
0x2d6f4  ldc.i4.s 0x2F
0x2d6f6  ldstr    aDo// "Do"
0x2d6fb  ldstr    aDA1SSrcCrmlive_55// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2d700  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganization(valuetype [mscorlib]System.Guid, int32, string, string)
0x2d705  stloc.2
0x2d706  ldloc.1
0x2d707  ldstr    aOrganization// "Organization"
0x2d70c  ldloc.2
0x2d70d  callvirt instance void Microsoft.Crm.Admin.AdminService.IOrganizationManifest::AddRow(string tableName, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag rowBag)
0x2d712  ldloc.2
0x2d713  ldstr    aUniquename// "UniqueName"
0x2d718  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2d71d  castclass [mscorlib]System.String
0x2d722  stloc.3
0x2d723  ldloc.3
0x2d724  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d729  brfalse.s loc_2D736
0x2d72b  ldstr    aOrganizationLa// "Organization lacks a Unique Name"
0x2d730  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2d735  throw
0x2d736  ldstr    aOrganizationfe_0// "OrganizationFeatureMap"
0x2d73b  ldstr    aOrganizationid_0// "OrganizationId"
0x2d740  ldarg.0
0x2d741  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::_organizationId
0x2d746  box      [mscorlib]System.Guid
0x2d74b  ldloc.1
0x2d74c  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddRowsByColumnEquality(string table, string column, object value, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d751  pop
0x2d752  ldarg.0
0x2d753  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::_organizationId
0x2d758  ldloc.1
0x2d759  call     object[] Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddSystemUserOrganizations(valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d75e  stloc.s  4
0x2d760  ldloc.s  4
0x2d762  brfalse.s loc_2D78F
0x2d764  ldloc.s  4
0x2d766  ldlen
0x2d767  brfalse.s loc_2D78F
0x2d769  ldstr    aSystemuser// "SystemUser"
0x2d76e  ldstr    aId// "Id"
0x2d773  ldloc.s  4
0x2d775  ldloc.1
0x2d776  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddRowsByColumnValues(string table, string columnName, object[] columnValues, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d77b  pop
0x2d77c  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x2d781  ldstr    aUserid// "UserId"
0x2d786  ldloc.s  4
0x2d788  ldloc.1
0x2d789  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddRowsByColumnValues(string table, string columnName, object[] columnValues, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d78e  pop
0x2d78f  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x2d794  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x2d799  ldc.i4.2
0x2d79a  bne.un   loc_2D840
0x2d79f  ldstr    aOrganizationre// "OrganizationResources"
0x2d7a4  ldstr    aOrganizationid_0// "OrganizationId"
0x2d7a9  ldarg.0
0x2d7aa  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::_organizationId
0x2d7af  box      [mscorlib]System.Guid
0x2d7b4  ldloc.1
0x2d7b5  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddRowsByColumnEquality(string table, string column, object value, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d7ba  pop
0x2d7bb  ldstr    aOrganizationna_0// "OrganizationNameStage"
0x2d7c0  ldstr    aOrganizationun// "OrganizationUniqueName"
0x2d7c5  ldloc.3
0x2d7c6  ldloc.1
0x2d7c7  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddRowsByColumnEquality(string table, string column, object value, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d7cc  pop
0x2d7cd  ldstr    aOrganizationli// "OrganizationLifecycle"
0x2d7d2  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x2d7d7  ldarg.0
0x2d7d8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::_organizationId
0x2d7dd  box      [mscorlib]System.Guid
0x2d7e2  ldloc.1
0x2d7e3  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddRowsByColumnEquality(string table, string column, object value, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d7e8  pop
0x2d7e9  ldstr    aServiceinstanc// "ServiceInstance"
0x2d7ee  ldstr    aOrganizationid_0// "OrganizationId"
0x2d7f3  ldarg.0
0x2d7f4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::_organizationId
0x2d7f9  box      [mscorlib]System.Guid
0x2d7fe  ldloc.1
0x2d7ff  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddRowsByColumnEquality(string table, string column, object value, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d804  pop
0x2d805  ldstr    aUserinvitation// "UserInvitation"
0x2d80a  ldstr    aOrganizationid_0// "OrganizationId"
0x2d80f  ldarg.0
0x2d810  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::_organizationId
0x2d815  box      [mscorlib]System.Guid
0x2d81a  ldloc.1
0x2d81b  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddRowsByColumnEquality(string table, string column, object value, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d820  pop
0x2d821  ldstr    aSystemuserrole// "SystemUserRoles"
0x2d826  ldstr    aSystemuserid// "SystemUserId"
0x2d82b  ldloc.s  4
0x2d82d  ldloc.1
0x2d82e  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddRowsByColumnValues(string table, string columnName, object[] columnValues, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d833  pop
0x2d834  ldarg.0
0x2d835  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::_organizationId
0x2d83a  ldloc.1
0x2d83b  call     void Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::AddEncryptedColumns(valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.Admin.AdminService.IOrganizationManifest manifest)
0x2d840  ldloc.1
0x2d841  ldarg.0
0x2d842  ldfld    string Microsoft.Crm.Admin.AdminService.ExportOrganizationManifestAction::_filePath
0x2d847  callvirt instance void Microsoft.Crm.Admin.AdminService.IOrganizationManifest::SaveToFile(string filePath)
0x2d84c  ret
```
