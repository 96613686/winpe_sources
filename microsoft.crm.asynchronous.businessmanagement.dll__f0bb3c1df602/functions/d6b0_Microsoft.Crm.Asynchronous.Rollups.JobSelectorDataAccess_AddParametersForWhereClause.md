# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::AddParametersForWhereClause

- ea: `0xd6b0`
- end: `0xd776`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::AddParametersForWhereClause`
- size: `198`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xd320`
- `0xd410`
- `0xd5a0`

## callees

- `0xc8f0`
- `0xd200`
- `0xd210`
- `0xd6b0`
- `0xe620`

## string_xrefs

- `0xd703`: `@bootstrapCompleted`
- `0xd757`: `@rollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xd6b0  ldarg.1
0xd6b1  ldstr    aSourceentityty// "@sourceEntityTypeCode"
0xd6b6  ldarg.0
0xd6b7  call     instance int32 Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_EntityTypeCode()
0xd6bc  box      [mscorlib]System.Int32
0xd6c1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd6c6  pop
0xd6c7  ldarg.1
0xd6c8  ldstr    aInitialstateco// "@initialStateCode"
0xd6cd  ldarg.0
0xd6ce  ldfld    valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_initialState
0xd6d3  box      [mscorlib]System.Int32
0xd6d8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd6dd  pop
0xd6de  ldarg.1
0xd6df  ldstr    aActivestatecod// "@activeStateCode"
0xd6e4  ldc.i4.0
0xd6e5  box      [mscorlib]System.Int32
0xd6ea  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd6ef  pop
0xd6f0  ldarg.1
0xd6f1  ldstr    aActivestatusco// "@activeStatusCode"
0xd6f6  ldc.i4.1
0xd6f7  box      [mscorlib]System.Int32
0xd6fc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd701  pop
0xd702  ldarg.1
0xd703  ldstr    aBootstrapcompl// "@bootstrapCompleted"
0xd708  ldc.i4.3
0xd709  box      [mscorlib]System.Int32
0xd70e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd713  pop
0xd714  ldarg.1
0xd715  ldstr    aDatetimenow// "@dateTimeNow"
0xd71a  ldarg.0
0xd71b  call     instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess()
0xd720  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::GetUTCDateWithoutMilliseconds()
0xd725  box      [mscorlib]System.DateTime
0xd72a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd72f  pop
0xd730  ldarg.1
0xd731  ldstr    aMaxretrycount_0// "@maxRetryCount"
0xd736  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_IncrementalRollupFailureMaxRetryCount()
0xd73b  box      [mscorlib]System.Int32
0xd740  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd745  pop
0xd746  ldarg.0
0xd747  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_rollupPropertiesId
0xd74c  stloc.0
0xd74d  ldloca.s 0
0xd74f  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xd754  brfalse.s loc_D775
0xd756  ldarg.1
0xd757  ldstr    aRollupproperti_0// "@rollupPropertiesId"
0xd75c  ldarg.0
0xd75d  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_rollupPropertiesId
0xd762  stloc.0
0xd763  ldloca.s 0
0xd765  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xd76a  box      [mscorlib]System.Guid
0xd76f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd774  pop
0xd775  ret
```
