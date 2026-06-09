# Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::CleanupExistingDatabase

- ea: `0x6ab0`
- end: `0x6cbb`
- name: `Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::CleanupExistingDatabase`
- size: `523`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6a00`
- `0x6a70`
- `0x6cc0`

## callees

- `0x64b0`
- `0x6ab0`
- `0x6d00`
- `0x91b0`
- `0x9410`

## string_xrefs

- `0x6ad9`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\DbInstallAction.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6ab0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x6ab5  stloc.0
0x6ab6  ldloc.0
0x6ab7  ldstr    aOrganization// "Organization"
0x6abc  ldarg.0
0x6abd  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6ac2  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6ac7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x6acc  box      [mscorlib]System.Guid
0x6ad1  ldnull
0x6ad2  ldc.i4.s 0x4E
0x6ad4  ldstr    aCleanupexistin// "CleanupExistingDatabase"
0x6ad9  ldstr    aDDbsShDccm2110_6// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x6ade  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x6ae3  stloc.1
0x6ae4  ldloc.1
0x6ae5  brtrue.s loc_6AEC
0x6ae7  leave    loc_6CBA
0x6aec  ldloc.1
0x6aed  ldstr    aSqlservername// "SqlServerName"
0x6af2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6af7  castclass [mscorlib]System.String
0x6afc  stloc.2
0x6afd  ldnull
0x6afe  stloc.3
0x6aff  ldloc.1
0x6b00  ldstr    aMirroredsqlser// "MirroredSqlServerName"
0x6b05  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6b0a  brfalse.s loc_6B1D
0x6b0c  ldloc.1
0x6b0d  ldstr    aMirroredsqlser// "MirroredSqlServerName"
0x6b12  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6b17  castclass [mscorlib]System.String
0x6b1c  stloc.3
0x6b1d  ldnull
0x6b1e  stloc.s  4
0x6b20  ldnull
0x6b21  stloc.s  5
0x6b23  ldnull
0x6b24  stloc.s  6
0x6b26  ldloc.1
0x6b27  ldstr    aAvailabilitygr// "AvailabilityGroupName"
0x6b2c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6b31  brfalse.s loc_6B6A
0x6b33  ldloc.1
0x6b34  ldstr    aAvailabilitygr// "AvailabilityGroupName"
0x6b39  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6b3e  castclass [mscorlib]System.String
0x6b43  stloc.s  4
0x6b45  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::.ctor()
0x6b4a  dup
0x6b4b  ldloc.s  4
0x6b4d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::GetIdFromName(string)
0x6b52  stloc.s  8
0x6b54  ldloc.s  8
0x6b56  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.AvailabilityGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::Retrieve(valuetype [mscorlib]System.Guid)
0x6b5b  dup
0x6b5c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::get_AsyncReplica1()
0x6b61  stloc.s  5
0x6b63  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::get_AsyncReplica2()
0x6b68  stloc.s  6
0x6b6a  ldloc.1
0x6b6b  ldstr    aDatabasename// "DatabaseName"
0x6b70  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6b75  castclass [mscorlib]System.String
0x6b7a  stloc.s  7
0x6b7c  ldarg.0
0x6b7d  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6b82  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6b87  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x6b8c  ldc.i4.s 0xA
0x6b8e  ldstr    aInCleanupexist// "In CleanupExistingDatabase, Organizatio"...
0x6b93  ldc.i4.6
0x6b94  newarr   [mscorlib]System.Object
0x6b99  dup
0x6b9a  ldc.i4.0
0x6b9b  ldarg.0
0x6b9c  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6ba1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6ba6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x6bab  box      [mscorlib]System.Guid
0x6bb0  stelem.ref
0x6bb1  dup
0x6bb2  ldc.i4.1
0x6bb3  ldloc.s  7
0x6bb5  stelem.ref
0x6bb6  dup
0x6bb7  ldc.i4.2
0x6bb8  ldloc.2
0x6bb9  stelem.ref
0x6bba  dup
0x6bbb  ldc.i4.3
0x6bbc  ldloc.3
0x6bbd  stelem.ref
0x6bbe  dup
0x6bbf  ldc.i4.4
0x6bc0  ldloc.s  5
0x6bc2  stelem.ref
0x6bc3  dup
0x6bc4  ldc.i4.5
0x6bc5  ldloc.s  6
0x6bc7  stelem.ref
0x6bc8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6bcd  ldloc.s  4
0x6bcf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6bd4  brtrue.s loc_6BE0
0x6bd6  ldloc.s  4
0x6bd8  ldloc.2
0x6bd9  ldloc.s  7
0x6bdb  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::RemovePrimaryDatabaseFromAvailabilityGroup(string, string, string)
0x6be0  ldloc.2
0x6be1  ldloc.s  7
0x6be3  ldarg.0
0x6be4  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6be9  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6bee  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0x6bf3  ldarg.0
0x6bf4  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6bf9  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6bfe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x6c03  ldarg.0
0x6c04  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6c09  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x6c0e  call     void Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::DropDatabase(string sqlServer, string databaseName, string connectionString, valuetype [mscorlib]System.Guid organizationId, bool isBackedByXdb)
0x6c13  ldloc.3
0x6c14  ldloc.s  7
0x6c16  ldarg.0
0x6c17  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6c1c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6c21  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0x6c26  ldarg.0
0x6c27  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6c2c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6c31  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x6c36  ldarg.0
0x6c37  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6c3c  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x6c41  call     void Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::DropDatabase(string sqlServer, string databaseName, string connectionString, valuetype [mscorlib]System.Guid organizationId, bool isBackedByXdb)
0x6c46  ldloc.s  5
0x6c48  ldloc.s  7
0x6c4a  ldarg.0
0x6c4b  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6c50  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6c55  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0x6c5a  ldarg.0
0x6c5b  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6c60  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6c65  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x6c6a  ldarg.0
0x6c6b  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6c70  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x6c75  call     void Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::DropDatabase(string sqlServer, string databaseName, string connectionString, valuetype [mscorlib]System.Guid organizationId, bool isBackedByXdb)
0x6c7a  ldloc.s  6
0x6c7c  ldloc.s  7
0x6c7e  ldarg.0
0x6c7f  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6c84  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6c89  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0x6c8e  ldarg.0
0x6c8f  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6c94  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6c99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x6c9e  ldarg.0
0x6c9f  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6ca4  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x6ca9  call     void Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::DropDatabase(string sqlServer, string databaseName, string connectionString, valuetype [mscorlib]System.Guid organizationId, bool isBackedByXdb)
0x6cae  leave.s  loc_6CBA
0x6cb0  ldloc.0
0x6cb1  brfalse.s loc_6CB9
0x6cb3  ldloc.0
0x6cb4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6cb9  endfinally
0x6cba  ret
```
