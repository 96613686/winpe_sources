# Microsoft.Crm.Asynchronous.OrgUpdateActions::DoBulkCopy

- ea: `0xd100`
- end: `0xd1cd`
- name: `Microsoft.Crm.Asynchronous.OrgUpdateActions::DoBulkCopy`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd080`

## callees

- `0xd100`
- `0xd1d0`

## string_xrefs

- `0xd144`: `\nselect \n	uat.[ActionId],\n	uat.[UpgradeToVersionNumber],\n	uat.[ExecutionOrder],\n	uat.[WasExecuted],\n	uat.[ActionName],\n	uat.[Description],\n	uat.[ExecutionTime],\n	uat.[HashFile],\n	uat.[HashValue],\n	uat.[CreatedOnUtc]\n	,@OrganizationId as OrganizationId\n	,convert(datetime, convert(time, uat.[ExecutionTime])) as ExecutionTimeAsDateTime \nfrom [dbo].[UpgradeActionTracker] uat with(nolock)\nwhere uat.UpgradeToVersionNumber = @UpgradeToVersionNumber`

## pseudocode

```c

```

## disassembly

```asm
0xd100  call     string Microsoft.Crm.Asynchronous.OrgUpdateActions::GetScaleGroupDBConnectionString()
0xd105  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmConfigDBConnection::.ctor(string)
0xd10a  stloc.0
0xd10b  ldloc.0
0xd10c  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0xd111  ldloc.0
0xd112  callvirt instance string [System.Data]System.Data.IDbConnection::get_ConnectionString()
0xd117  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseMetadata::RemoveProviderFromConnectionString(string)
0xd11c  newobj   instance void [System.Data]System.Data.SqlClient.SqlBulkCopy::.ctor(string)
0xd121  stloc.1
0xd122  ldloc.1
0xd123  ldstr    aDboUpgradeacti// "dbo.UpgradeActionTrackerForAllScaleGrou"...
0xd128  callvirt instance void [System.Data]System.Data.SqlClient.SqlBulkCopy::set_DestinationTableName(string)
0xd12d  ldarg.0
0xd12e  ldc.i4.0
0xd12f  ldc.i4.0
0xd130  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xd135  stloc.2
0xd136  ldloc.2
0xd137  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xd13c  ldloc.2
0xd13d  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0xd142  stloc.3
0xd143  ldloc.3
0xd144  ldstr    aSelectUatActio// "\r\nselect \r\n\tuat.[ActionId],\r\n\tu"...
0xd149  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd14e  ldloc.3
0xd14f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd154  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd159  ldstr    aOrganizationid_2// "@OrganizationId"
0xd15e  ldarg.0
0xd15f  box      [mscorlib]System.Guid
0xd164  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd169  pop
0xd16a  ldloc.3
0xd16b  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd170  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd175  ldstr    aUpgradetoversi// "@UpgradeToVersionNumber"
0xd17a  ldarg.1
0xd17b  callvirt instance string [mscorlib]System.Object::ToString()
0xd180  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd185  pop
0xd186  ldloc.3
0xd187  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0xd18c  stloc.s  4
0xd18e  ldloc.1
0xd18f  ldloc.s  4
0xd191  callvirt instance void [System.Data]System.Data.SqlClient.SqlBulkCopy::WriteToServer(class [System.Data]System.Data.IDataReader)
0xd196  leave.s  loc_D1CC
0xd198  ldloc.s  4
0xd19a  brfalse.s loc_D1A3
0xd19c  ldloc.s  4
0xd19e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1a3  endfinally
0xd1a4  ldloc.3
0xd1a5  brfalse.s loc_D1AD
0xd1a7  ldloc.3
0xd1a8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1ad  endfinally
0xd1ae  ldloc.2
0xd1af  brfalse.s loc_D1B7
0xd1b1  ldloc.2
0xd1b2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1b7  endfinally
0xd1b8  ldloc.1
0xd1b9  brfalse.s loc_D1C1
0xd1bb  ldloc.1
0xd1bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1c1  endfinally
0xd1c2  ldloc.0
0xd1c3  brfalse.s loc_D1CB
0xd1c5  ldloc.0
0xd1c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1cb  endfinally
0xd1cc  ret
```
