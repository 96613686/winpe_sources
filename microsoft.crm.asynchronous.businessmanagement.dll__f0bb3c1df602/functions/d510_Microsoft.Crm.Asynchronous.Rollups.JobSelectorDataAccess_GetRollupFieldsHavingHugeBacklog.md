# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetRollupFieldsHavingHugeBacklog

- ea: `0xd510`
- end: `0xd595`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetRollupFieldsHavingHugeBacklog`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xc310`

## callees

- `0xca50`
- `0xd210`
- `0xd510`
- `0xe630`
- `0x16f90`

## string_xrefs

- `0xd528`: `SELECT \n												RollupPropertiesId \n											FROM \n												RollupJobBase WITH (NOLOCK) \n											WHERE \n												StateCode = @initialState \n											GROUP BY \n												RollupPropertiesId \n											HAVING \n												COUNT(RollupJobId) >= @maxRollupJobCount`

## pseudocode

```c

```

## disassembly

```asm
0xd510  newobj   instance void <>c__DisplayClass17_0::.ctor()
0xd515  stloc.0
0xd516  ldloc.0
0xd517  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xd51c  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass17_0::rollupPropertiesList
0xd521  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xd526  stloc.1
0xd527  ldloc.1
0xd528  ldstr    aSelectRolluppr// "SELECT \r\n\t\t\t\t\t\t\t\t\t\t\t\tRoll"...
0xd52d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd532  ldloc.1
0xd533  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd538  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd53d  dup
0xd53e  ldstr    aMaxrollupjobco// "@maxRollupJobCount"
0xd543  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_MaxAllowedPendingRollupJobs()
0xd548  box      [mscorlib]System.Int32
0xd54d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd552  pop
0xd553  ldstr    aInitialstate// "@initialState"
0xd558  ldarg.0
0xd559  ldfld    valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_initialState
0xd55e  box      [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState
0xd563  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd568  pop
0xd569  ldarg.0
0xd56a  call     instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess()
0xd56f  ldloc.1
0xd570  ldloc.0
0xd571  ldftn    instance void <>c__DisplayClass17_0::<GetRollupFieldsHavingHugeBacklog>b__0(object[] values)
0xd577  newobj   instance void class [mscorlib]System.Action`1<object[]>::.ctor(object, native int)
0xd57c  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand command, class [mscorlib]System.Action`1<object[]> recordProcessor)
0xd581  pop
0xd582  leave.s  loc_D58E
0xd584  ldloc.1
0xd585  brfalse.s loc_D58D
0xd587  ldloc.1
0xd588  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd58d  endfinally
0xd58e  ldloc.0
0xd58f  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass17_0::rollupPropertiesList
0xd594  ret
```
