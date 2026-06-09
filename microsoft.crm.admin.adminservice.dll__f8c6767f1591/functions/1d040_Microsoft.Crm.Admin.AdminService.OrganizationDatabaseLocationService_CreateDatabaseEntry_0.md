# Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocationService::CreateDatabaseEntry_0

- ea: `0x1d040`
- end: `0x1d19e`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocationService::CreateDatabaseEntry_0`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d030`

## callees

- `0x1d040`
- `0x1dba0`
- `0x38ec0`
- `0x38ee0`
- `0x38f00`
- `0x38f20`

## string_xrefs

- `0x1d08c`: `INSERT INTO dbo.OrganizationDatabaseLocation (Id, organizationid, logicalserver, databasename, connectionstring, region, isprimary, isAvailableForRestore, isdeleted, isSoftDeleted) \n					 VALUES (@id, @orgid, @logicalserver, @databasename, @connectionstring, @region, @isPrimary, @isAvailableForRestore, @isdeleted, @isSoftDeleted)`
- `0x1d157`: `@isdeleted`
- `0x1d16e`: `isSoftDeleted`

## pseudocode

```c

```

## disassembly

```asm
0x1d040  ldarg.1
0x1d041  ldstr    aOrganizationid// "organizationId"
0x1d046  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1d04b  ldarg.2
0x1d04c  ldstr    aIdentifier// "identifier"
0x1d051  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d056  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1d05b  stloc.0
0x1d05c  call     bool Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocationService::IsSqlAzureDatabaseSetup()
0x1d061  brtrue.s loc_1D081
0x1d063  ldnull
0x1d064  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d069  ldc.i4.s 0x45
0x1d06b  ldstr    aOrganizationda// " OrganizationDatabaseLocation is not se"...
0x1d070  ldc.i4.0
0x1d071  newarr   [mscorlib]System.Object
0x1d076  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d07b  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1d080  ret
0x1d081  ldsfld   string Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocationService::_connectionString
0x1d086  call     class [System.Data]System.Data.SqlClient.SqlConnection [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAadConnectionProvider::CreateOpenConnection(string)
0x1d08b  stloc.1
0x1d08c  ldstr    aInsertIntoDboO// "INSERT INTO dbo.OrganizationDatabaseLoc"...
0x1d091  ldloc.1
0x1d092  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x1d097  stloc.2
0x1d098  ldloc.2
0x1d099  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d09e  ldstr    aId_1// "@id"
0x1d0a3  ldloc.0
0x1d0a4  box      [mscorlib]System.Guid
0x1d0a9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d0ae  pop
0x1d0af  ldloc.2
0x1d0b0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d0b5  ldstr    aOrgid_1// "@orgid"
0x1d0ba  ldarg.1
0x1d0bb  box      [mscorlib]System.Guid
0x1d0c0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d0c5  pop
0x1d0c6  ldloc.2
0x1d0c7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d0cc  ldstr    aLogicalserver// "@logicalServer"
0x1d0d1  ldarg.2
0x1d0d2  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x1d0d7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d0dc  pop
0x1d0dd  ldloc.2
0x1d0de  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d0e3  ldstr    aDatabasename_2// "@databaseName"
0x1d0e8  ldarg.2
0x1d0e9  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x1d0ee  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d0f3  pop
0x1d0f4  ldloc.2
0x1d0f5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d0fa  ldstr    aConnectionstri_0// "@connectionString"
0x1d0ff  ldarg.2
0x1d100  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_ConnectionString()
0x1d105  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d10a  pop
0x1d10b  ldloc.2
0x1d10c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d111  ldstr    aRegion// "@region"
0x1d116  ldarg.2
0x1d117  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x1d11c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d121  pop
0x1d122  ldloc.2
0x1d123  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d128  ldstr    aIsprimary_0// "@isprimary"
0x1d12d  ldarg.3
0x1d12e  box      [mscorlib]System.Boolean
0x1d133  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d138  pop
0x1d139  ldloc.2
0x1d13a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d13f  ldstr    aIsavailablefor// "@isAvailableForRestore"
0x1d144  ldarg.s  4
0x1d146  box      [mscorlib]System.Boolean
0x1d14b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d150  pop
0x1d151  ldloc.2
0x1d152  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d157  ldstr    aIsdeleted// "@isdeleted"
0x1d15c  ldc.i4.0
0x1d15d  box      [mscorlib]System.Boolean
0x1d162  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d167  pop
0x1d168  ldloc.2
0x1d169  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d16e  ldstr    aIssoftdeleted// "isSoftDeleted"
0x1d173  ldc.i4.0
0x1d174  box      [mscorlib]System.Boolean
0x1d179  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d17e  pop
0x1d17f  ldloc.2
0x1d180  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x1d185  pop
0x1d186  leave.s  loc_1D19C
0x1d188  ldloc.2
0x1d189  brfalse.s loc_1D191
0x1d18b  ldloc.2
0x1d18c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d191  endfinally
0x1d192  ldloc.1
0x1d193  brfalse.s loc_1D19B
0x1d195  ldloc.1
0x1d196  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d19b  endfinally
0x1d19c  ldloc.0
0x1d19d  ret
```
