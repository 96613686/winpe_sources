# <>c__DisplayClass2_0::<GrantAccessBulkForCreate>b__0

- ea: `0x8f490`
- end: `0x8f582`
- name: `<>c__DisplayClass2_0::<GrantAccessBulkForCreate>b__0`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1e020`
- `0x66af0`
- `0x66b00`
- `0x6dbb0`
- `0x8f490`

## string_xrefs

- `0x8f55a`: `GrantAccessBulkForCreate`
- `0x8f539`: `@access_rights`
- `0x8f49b`: `exec p_GrantAccessBulkForCreate @objectId, @objectTypeCode, @principal_ids, @principal_type, @access_rights`

## pseudocode

```c

```

## disassembly

```asm
0x8f490  ldarg.0
0x8f491  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x8f496  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x8f49b  ldstr    aExecPGrantacce// "exec p_GrantAccessBulkForCreate @object"...
0x8f4a0  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x8f4a5  stloc.0
0x8f4a6  ldloc.0
0x8f4a7  ldarg.0
0x8f4a8  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x8f4ad  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8f4b2  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x8f4b7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x8f4bc  ldloc.0
0x8f4bd  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x8f4c2  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x8f4c7  dup
0x8f4c8  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x8f4cd  dup
0x8f4ce  ldstr    aObjectid_4// "@objectId"
0x8f4d3  ldc.i4.s 0xE
0x8f4d5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x8f4da  ldarg.0
0x8f4db  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::objectId
0x8f4e0  box      [mscorlib]System.Guid
0x8f4e5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x8f4ea  dup
0x8f4eb  ldstr    aObjecttypecode_84// "@objectTypeCode"
0x8f4f0  ldc.i4.8
0x8f4f1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x8f4f6  ldarg.0
0x8f4f7  ldfld    int32 <>c__DisplayClass2_0::objectTypeCode
0x8f4fc  box      [mscorlib]System.Int32
0x8f501  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x8f506  dup
0x8f507  ldarg.0
0x8f508  ldfld    valuetype [mscorlib]System.Guid[] <>c__DisplayClass2_0::principalIds
0x8f50d  ldstr    aPrincipalIds// "@principal_ids"
0x8f512  call     class [System.Data]System.Data.SqlClient.SqlParameter Microsoft.Crm.Query.QueryHelper::GetSqlParameterForManyGuidsUsingTableValuedParameter(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> values, string parameterName)
0x8f517  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x8f51c  pop
0x8f51d  dup
0x8f51e  ldstr    aPrincipalType// "@principal_type"
0x8f523  ldc.i4.8
0x8f524  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x8f529  ldarg.0
0x8f52a  ldfld    int32 <>c__DisplayClass2_0::principalType
0x8f52f  box      [mscorlib]System.Int32
0x8f534  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x8f539  ldstr    aAccessRights// "@access_rights"
0x8f53e  ldc.i4.8
0x8f53f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x8f544  ldarg.0
0x8f545  ldfld    int32 <>c__DisplayClass2_0::accessMask
0x8f54a  box      [mscorlib]System.Int32
0x8f54f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x8f554  ldloc.0
0x8f555  ldc.i4   0x1B5
0x8f55a  ldstr    aGrantaccessbul// "GrantAccessBulkForCreate"
0x8f55f  ldstr    aDA1SSrcManaged_14// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x8f564  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x8f569  pop
0x8f56a  ldarg.0
0x8f56b  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x8f570  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RegisterHandlerAndTrackPOA(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8f575  leave.s  loc_8F581
0x8f577  ldloc.0
0x8f578  brfalse.s loc_8F580
0x8f57a  ldloc.0
0x8f57b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8f580  endfinally
0x8f581  ret
```
