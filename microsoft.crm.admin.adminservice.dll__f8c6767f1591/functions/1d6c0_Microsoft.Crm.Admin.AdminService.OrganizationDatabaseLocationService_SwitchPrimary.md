# Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocationService::SwitchPrimary

- ea: `0x1d6c0`
- end: `0x1d830`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocationService::SwitchPrimary`
- size: `368`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1d6c0`
- `0x1dba0`

## string_xrefs

- `0x1d727`: `UPDATE dbo.OrganizationDatabaseLocation SET IsPrimary = 0 WHERE OrganizationId = @orgid and Id = @oldId`
- `0x1d78e`: `UPDATE dbo.OrganizationDatabaseLocation SET IsPrimary = 1 WHERE OrganizationId = @orgid and Id = @newId`
- `0x1d7bc`: `Could not update database with ID {0} to be primary for the organizationId {1}. please check if the database record exists in the OrganizationDatabaseLocation table`
- `0x1d7dd`: `Could not update database with ID {0} to be primary for organization {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1d6c0  ldarg.1
0x1d6c1  ldstr    aOrganizationid// "organizationId"
0x1d6c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1d6cb  ldarg.2
0x1d6cc  ldstr    aOldprimarykeyi// "oldPrimaryKeyId"
0x1d6d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1d6d6  ldarg.3
0x1d6d7  ldstr    aNewprimarykeyi// "newPrimaryKeyId"
0x1d6dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1d6e1  call     bool Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocationService::IsSqlAzureDatabaseSetup()
0x1d6e6  brtrue.s loc_1D701
0x1d6e8  ldnull
0x1d6e9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d6ee  ldc.i4.s 0x45
0x1d6f0  ldstr    aOrganizationda// " OrganizationDatabaseLocation is not se"...
0x1d6f5  ldc.i4.0
0x1d6f6  newarr   [mscorlib]System.Object
0x1d6fb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d700  ret
0x1d701  ldsfld   string Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocationService::_connectionString
0x1d706  call     class [System.Data]System.Data.SqlClient.SqlConnection [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAadConnectionProvider::CreateOpenConnection(string)
0x1d70b  stloc.0
0x1d70c  ldloc.0
0x1d70d  ldstr    aSwitchprimary// "SwitchPrimary"
0x1d712  callvirt instance class [System.Data]System.Data.SqlClient.SqlTransaction [System.Data]System.Data.SqlClient.SqlConnection::BeginTransaction(string)
0x1d717  stloc.1
0x1d718  ldloc.0
0x1d719  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand [System.Data]System.Data.SqlClient.SqlConnection::CreateCommand()
0x1d71e  stloc.2
0x1d71f  ldloc.2
0x1d720  ldloc.1
0x1d721  callvirt instance void [System.Data]System.Data.SqlClient.SqlCommand::set_Transaction(class [System.Data]System.Data.SqlClient.SqlTransaction)
0x1d726  ldloc.2
0x1d727  ldstr    aUpdateDboOrgan_0// "UPDATE dbo.OrganizationDatabaseLocation"...
0x1d72c  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x1d731  ldloc.2
0x1d732  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d737  ldstr    aOrgid_1// "@orgid"
0x1d73c  ldarg.1
0x1d73d  box      [mscorlib]System.Guid
0x1d742  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d747  pop
0x1d748  ldloc.2
0x1d749  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d74e  ldstr    aOldid// "@oldId"
0x1d753  ldarg.2
0x1d754  box      [mscorlib]System.Guid
0x1d759  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d75e  pop
0x1d75f  ldloc.2
0x1d760  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x1d765  ldc.i4.0
0x1d766  bgt.s    loc_1D78D
0x1d768  ldnull
0x1d769  ldarg.1
0x1d76a  ldc.i4.s 0x45
0x1d76c  ldstr    aTheDatabaseWit// " The database with Id {0} given does no"...
0x1d771  ldarg.2
0x1d772  box      [mscorlib]System.Guid
0x1d777  ldarg.1
0x1d778  box      [mscorlib]System.Guid
0x1d77d  call     string [mscorlib]System.String::Format(string, object, object)
0x1d782  ldc.i4.0
0x1d783  newarr   [mscorlib]System.Object
0x1d788  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d78d  ldloc.2
0x1d78e  ldstr    aUpdateDboOrgan_1// "UPDATE dbo.OrganizationDatabaseLocation"...
0x1d793  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x1d798  ldloc.2
0x1d799  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x1d79e  ldstr    aNewid// "@newId"
0x1d7a3  ldarg.3
0x1d7a4  box      [mscorlib]System.Guid
0x1d7a9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d7ae  pop
0x1d7af  ldloc.2
0x1d7b0  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x1d7b5  ldc.i4.0
0x1d7b6  bgt.s    loc_1D7F9
0x1d7b8  ldnull
0x1d7b9  ldarg.1
0x1d7ba  ldc.i4.s 0x45
0x1d7bc  ldstr    aCouldNotUpdate// "Could not update database with ID {0} t"...
0x1d7c1  ldarg.3
0x1d7c2  box      [mscorlib]System.Guid
0x1d7c7  ldarg.1
0x1d7c8  box      [mscorlib]System.Guid
0x1d7cd  call     string [mscorlib]System.String::Format(string, object, object)
0x1d7d2  ldc.i4.0
0x1d7d3  newarr   [mscorlib]System.Object
0x1d7d8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d7dd  ldstr    aCouldNotUpdate_0// "Could not update database with ID {0} t"...
0x1d7e2  ldarg.3
0x1d7e3  box      [mscorlib]System.Guid
0x1d7e8  ldarg.1
0x1d7e9  box      [mscorlib]System.Guid
0x1d7ee  call     string [mscorlib]System.String::Format(string, object, object)
0x1d7f3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1d7f8  throw
0x1d7f9  leave.s  loc_1D805
0x1d7fb  ldloc.2
0x1d7fc  brfalse.s loc_1D804
0x1d7fe  ldloc.2
0x1d7ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d804  endfinally
0x1d805  ldloc.1
0x1d806  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x1d80b  leave.s  loc_1D82F
0x1d80d  pop
0x1d80e  ldloc.1
0x1d80f  ldstr    aSwitchprimary// "SwitchPrimary"
0x1d814  callvirt instance void [System.Data]System.Data.SqlClient.SqlTransaction::Rollback(string)
0x1d819  rethrow
0x1d81b  ldloc.1
0x1d81c  brfalse.s loc_1D824
0x1d81e  ldloc.1
0x1d81f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d824  endfinally
0x1d825  ldloc.0
0x1d826  brfalse.s loc_1D82E
0x1d828  ldloc.0
0x1d829  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d82e  endfinally
0x1d82f  ret
```
