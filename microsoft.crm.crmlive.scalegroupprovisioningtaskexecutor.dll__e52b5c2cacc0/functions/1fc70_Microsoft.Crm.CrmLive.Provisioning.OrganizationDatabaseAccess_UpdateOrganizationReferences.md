# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateOrganizationReferences

- ea: `0x1fc70`
- end: `0x1feb6`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateOrganizationReferences`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1d6a0`

## callees

- `0x9190`
- `0x91b0`
- `0x9480`
- `0x126a0`
- `0x126e0`
- `0x1c370`
- `0x1c3b0`
- `0x1fc70`
- `0x24250`

## string_xrefs

- `0x1fcb0`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x1fcab`: `UpdateOrganizationReferences`
- `0x1fd12`: `update OrganizationBase set Name = @uniquename, CreatedOn = GETUTCDATE(), ModifiedOn = GETUTCDATE();`
- `0x1fd5d`: `update BusinessUnitBase set Name = @uniquename where ParentBusinessUnitId is null;`
- `0x1fd74`: `update TeamBase set Name = @uniquename where IsDefault = 1 and BusinessUnitId in (select BusinessUnitId from BusinessUnitBase where ParentBusinessUnitId is null);`
- `0x1fd8b`: `update OwnerBase set Name = @uniquename where OwnerId in (select TeamId from TeamBase where Name=@uniquename);`
- `0x1fda2`: `update MailboxBase set Name=@uniquenameAngle,RegardingObjectIdName=@uniquenameAngle where OwnerId in (select TeamId from TeamBase where Name=@uniquename);`
- `0x1fdc6`: `update ResourceGroupBase set Name=@uniquename where ResourceGroupId in (select TeamId from TeamBase where Name=@uniquename);`
- `0x1fe2a`: `update SiteBase set OrganizationId = @neworgid;`
- `0x1fe43`: `update PrincipalObjectAccess set PrincipalId = @neworgid where PrincipalId = @oldorgid and PrincipalTypeCode = 1019;`
- `0x1fe5a`: `update MetadataSchema.OrganizationLanguagePack set OrganizationId = @neworgid where OrganizationId = @oldorgid;`
- `0x1fe71`: `update SystemUserPrincipals set PrincipalId  = @neworgid where PrincipalId  = @oldorgid;`

## pseudocode

```c

```

## disassembly

```asm
0x1fc70  ldarg.0
0x1fc71  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_DomainName()
0x1fc76  stloc.1
0x1fc77  ldarg.0
0x1fc78  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1fc7d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1fc82  ldc.i4.0
0x1fc83  ldc.i4.0
0x1fc84  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1fc89  stloc.2
0x1fc8a  ldloc.2
0x1fc8b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1fc90  ldloc.2
0x1fc91  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1fc96  stloc.s  5
0x1fc98  ldloc.s  5
0x1fc9a  ldstr    aSelectOrganiza// "select OrganizationId from Organization"...
0x1fc9f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fca4  ldloc.s  5
0x1fca6  ldc.i4   0xBCE
0x1fcab  ldstr    aUpdateorganiza_0// "UpdateOrganizationReferences"
0x1fcb0  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1fcb5  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1fcba  unbox.any [mscorlib]System.Guid
0x1fcbf  stloc.0
0x1fcc0  leave.s  loc_1FCCE
0x1fcc2  ldloc.s  5
0x1fcc4  brfalse.s loc_1FCCD
0x1fcc6  ldloc.s  5
0x1fcc8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fccd  endfinally
0x1fcce  ldnull
0x1fccf  stloc.3
0x1fcd0  ldloca.s 0
0x1fcd2  ldarg.0
0x1fcd3  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1fcd8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1fcdd  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x1fce2  ldc.i4.0
0x1fce3  ceq
0x1fce5  stloc.s  4
0x1fce7  ldloc.s  4
0x1fce9  brfalse.s loc_1FD08
0x1fceb  ldloc.2
0x1fcec  ldloc.3
0x1fced  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, string[] uniqueIndexFields)
0x1fcf2  ldstr    aOrganization_1// "organization"
0x1fcf7  ldloc.0
0x1fcf8  ldarg.0
0x1fcf9  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1fcfe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1fd03  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::ChangePrimaryKey(string entityName, valuetype [mscorlib]System.Guid oldId, valuetype [mscorlib]System.Guid newId)
0x1fd08  ldloc.2
0x1fd09  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1fd0e  stloc.s  6
0x1fd10  ldloc.s  6
0x1fd12  ldstr    aUpdateOrganiza_0// "update OrganizationBase set Name = @uni"...
0x1fd17  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fd1c  ldloc.s  6
0x1fd1e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1fd23  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1fd28  stloc.s  7
0x1fd2a  ldloc.s  7
0x1fd2c  ldstr    aUniquename_0// "uniquename"
0x1fd31  ldloc.1
0x1fd32  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1fd37  pop
0x1fd38  ldloc.s  7
0x1fd3a  ldstr    aUniquenameangl// "uniquenameAngle"
0x1fd3f  ldstr    asc_4C552// "<"
0x1fd44  ldloc.1
0x1fd45  ldstr    asc_4C556// ">"
0x1fd4a  call     string [mscorlib]System.String::Concat(string, string, string)
0x1fd4f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1fd54  pop
0x1fd55  ldloc.s  6
0x1fd57  dup
0x1fd58  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1fd5d  ldstr    aUpdateBusiness_0// "update BusinessUnitBase set Name = @uni"...
0x1fd62  call     string [mscorlib]System.String::Concat(string, string)
0x1fd67  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fd6c  ldloc.s  6
0x1fd6e  dup
0x1fd6f  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1fd74  ldstr    aUpdateTeambase_0// "update TeamBase set Name = @uniquename "...
0x1fd79  call     string [mscorlib]System.String::Concat(string, string)
0x1fd7e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fd83  ldloc.s  6
0x1fd85  dup
0x1fd86  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1fd8b  ldstr    aUpdateOwnerbas// "update OwnerBase set Name = @uniquename"...
0x1fd90  call     string [mscorlib]System.String::Concat(string, string)
0x1fd95  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fd9a  ldloc.s  6
0x1fd9c  dup
0x1fd9d  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1fda2  ldstr    aUpdateMailboxb_0// "update MailboxBase set Name=@uniquename"...
0x1fda7  call     string [mscorlib]System.String::Concat(string, string)
0x1fdac  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fdb1  ldarg.0
0x1fdb2  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OriginalCreateInfo()
0x1fdb7  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_IsXrm()
0x1fdbc  brtrue.s loc_1FDD5
0x1fdbe  ldloc.s  6
0x1fdc0  dup
0x1fdc1  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1fdc6  ldstr    aUpdateResource// "update ResourceGroupBase set Name=@uniq"...
0x1fdcb  call     string [mscorlib]System.String::Concat(string, string)
0x1fdd0  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fdd5  ldloc.s  6
0x1fdd7  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1fddc  pop
0x1fddd  ldloc.s  4
0x1fddf  brfalse  loc_1FE9D
0x1fde4  ldloc.s  7
0x1fde6  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x1fdeb  ldloc.s  7
0x1fded  ldstr    aOldorgid// "oldorgid"
0x1fdf2  ldloc.0
0x1fdf3  box      [mscorlib]System.Guid
0x1fdf8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1fdfd  pop
0x1fdfe  ldloc.s  7
0x1fe00  ldstr    aNeworgid// "neworgid"
0x1fe05  ldarg.0
0x1fe06  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1fe0b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1fe10  box      [mscorlib]System.Guid
0x1fe15  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1fe1a  pop
0x1fe1b  ldloc.s  6
0x1fe1d  ldarg.0
0x1fe1e  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OriginalCreateInfo()
0x1fe23  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_IsXrm()
0x1fe28  brtrue.s loc_1FE31
0x1fe2a  ldstr    aUpdateSitebase// "update SiteBase set OrganizationId = @n"...
0x1fe2f  br.s     loc_1FE36
0x1fe31  ldsfld   string [mscorlib]System.String::Empty
0x1fe36  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fe3b  ldloc.s  6
0x1fe3d  dup
0x1fe3e  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1fe43  ldstr    aUpdatePrincipa// "update PrincipalObjectAccess set Princi"...
0x1fe48  call     string [mscorlib]System.String::Concat(string, string)
0x1fe4d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fe52  ldloc.s  6
0x1fe54  dup
0x1fe55  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1fe5a  ldstr    aUpdateMetadata_0// "update MetadataSchema.OrganizationLangu"...
0x1fe5f  call     string [mscorlib]System.String::Concat(string, string)
0x1fe64  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fe69  ldloc.s  6
0x1fe6b  dup
0x1fe6c  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1fe71  ldstr    aUpdateSystemus_3// "update SystemUserPrincipals set Princip"...
0x1fe76  call     string [mscorlib]System.String::Concat(string, string)
0x1fe7b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1fe80  ldloc.s  6
0x1fe82  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1fe87  pop
0x1fe88  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x1fe8d  ldarg.0
0x1fe8e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1fe93  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1fe98  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::UpdateActiveDirectoryGroupsForOnebox(valuetype [mscorlib]System.Guid organizationId)
0x1fe9d  leave.s  loc_1FEB5
0x1fe9f  ldloc.s  6
0x1fea1  brfalse.s loc_1FEAA
0x1fea3  ldloc.s  6
0x1fea5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1feaa  endfinally
0x1feab  ldloc.2
0x1feac  brfalse.s loc_1FEB4
0x1feae  ldloc.2
0x1feaf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1feb4  endfinally
0x1feb5  ret
```
