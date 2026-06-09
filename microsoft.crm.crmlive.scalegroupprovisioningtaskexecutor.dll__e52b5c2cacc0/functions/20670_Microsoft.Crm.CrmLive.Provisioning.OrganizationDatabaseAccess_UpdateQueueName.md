# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateQueueName

- ea: `0x20670`
- end: `0x207c3`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateQueueName`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1d6a0`

## callees

- `0x9190`
- `0x91b0`
- `0x9250`
- `0x1d3e0`
- `0x20670`

## string_xrefs

- `0x20722`: `update QueueBase set Description = @description, Name=@name where OwnerId = @ownerid`
- `0x20798`: `update QueueBase set Description=@description, Name=@name where OwnerId in (select TeamId from TeamBase where Name=@orgName)`

## pseudocode

```c

```

## disassembly

```asm
0x20670  ldarg.0
0x20671  ldarg.1
0x20672  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x20677  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x2067c  call     instance class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string> Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetInitialCrmSystemUserIdAndFullName(valuetype [mscorlib]System.Guid orgId)
0x20681  dup
0x20682  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::get_Item1()
0x20687  stloc.0
0x20688  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::get_Item2()
0x2068d  stloc.1
0x2068e  ldloc.1
0x2068f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x20694  brfalse.s loc_206B7
0x20696  ldarg.1
0x20697  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x2069c  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_FirstName()
0x206a1  ldstr    asc_35406// " "
0x206a6  ldarg.1
0x206a7  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x206ac  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_LastName()
0x206b1  call     string [mscorlib]System.String::Concat(string, string, string)
0x206b6  stloc.1
0x206b7  ldstr    asc_4C552// "<"
0x206bc  ldloc.1
0x206bd  ldstr    asc_4C556// ">"
0x206c2  call     string [mscorlib]System.String::Concat(string, string, string)
0x206c7  stloc.2
0x206c8  ldarg.1
0x206c9  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x206ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x206d3  ldc.i4.0
0x206d4  ldc.i4.0
0x206d5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x206da  stloc.3
0x206db  ldloc.3
0x206dc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x206e1  ldloc.3
0x206e2  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x206e7  stloc.s  5
0x206e9  ldloc.s  5
0x206eb  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x206f0  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x206f5  dup
0x206f6  ldstr    aDescription// "description"
0x206fb  ldloc.1
0x206fc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20701  pop
0x20702  dup
0x20703  ldstr    aName_0// "name"
0x20708  ldloc.2
0x20709  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2070e  pop
0x2070f  ldstr    aOwnerid// "ownerid"
0x20714  ldloc.0
0x20715  box      [mscorlib]System.Guid
0x2071a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2071f  pop
0x20720  ldloc.s  5
0x20722  ldstr    aUpdateQueuebas// "update QueueBase set Description = @des"...
0x20727  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2072c  ldloc.s  5
0x2072e  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x20733  pop
0x20734  leave.s  loc_20742
0x20736  ldloc.s  5
0x20738  brfalse.s loc_20741
0x2073a  ldloc.s  5
0x2073c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20741  endfinally
0x20742  ldarg.1
0x20743  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_DomainName()
0x20748  stloc.s  4
0x2074a  ldloc.3
0x2074b  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x20750  stloc.s  6
0x20752  ldloc.s  6
0x20754  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x20759  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2075e  dup
0x2075f  ldstr    aDescription// "description"
0x20764  ldloc.s  4
0x20766  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2076b  pop
0x2076c  dup
0x2076d  ldstr    aName_0// "name"
0x20772  ldstr    asc_4C552// "<"
0x20777  ldloc.s  4
0x20779  ldstr    asc_4C556// ">"
0x2077e  call     string [mscorlib]System.String::Concat(string, string, string)
0x20783  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20788  pop
0x20789  ldstr    aOrgname// "orgName"
0x2078e  ldloc.s  4
0x20790  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20795  pop
0x20796  ldloc.s  6
0x20798  ldstr    aUpdateQueuebas_0// "update QueueBase set Description=@descr"...
0x2079d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x207a2  ldloc.s  6
0x207a4  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x207a9  pop
0x207aa  leave.s  loc_207C2
0x207ac  ldloc.s  6
0x207ae  brfalse.s loc_207B7
0x207b0  ldloc.s  6
0x207b2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x207b7  endfinally
0x207b8  ldloc.3
0x207b9  brfalse.s loc_207C1
0x207bb  ldloc.3
0x207bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x207c1  endfinally
0x207c2  ret
```
