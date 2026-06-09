# Microsoft.Crm.Metadata.SecurityHelper::AddPrivilegeIdForObjectTypeCode

- ea: `0x5a2f0`
- end: `0x5a382`
- name: `Microsoft.Crm.Metadata.SecurityHelper::AddPrivilegeIdForObjectTypeCode`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x59df0`
- `0x5a280`

## callees

- `0x5a2f0`

## string_xrefs

- `0x5a36b`: `Create`
- `0x5a303`: `@privilegeid`
- `0x5a337`: `@privilegeid`
- `0x5a35d`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SecurityHelper.cs`
- `0x5a32a`: `insert PrivilegeObjectTypeCodes ( PrivilegeId, ObjectTypeCode) values ({0},{1})`
- `0x5a358`: `AddPrivilegeIdForObjectTypeCode`

## pseudocode

```c

```

## disassembly

```asm
0x5a2f0  ldarg.2
0x5a2f1  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x5a2f6  stloc.0
0x5a2f7  ldloc.0
0x5a2f8  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x5a2fd  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x5a302  dup
0x5a303  ldstr    aPrivilegeid_0// "@privilegeid"
0x5a308  ldarg.0
0x5a309  box      [mscorlib]System.Guid
0x5a30e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5a313  pop
0x5a314  ldstr    aObjecttypecode_1// "@objecttypecode"
0x5a319  ldarg.1
0x5a31a  box      [mscorlib]System.Int32
0x5a31f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5a324  pop
0x5a325  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a32a  ldstr    aInsertPrivileg// "insert PrivilegeObjectTypeCodes ( Privi"...
0x5a32f  ldc.i4.2
0x5a330  newarr   [mscorlib]System.Object
0x5a335  dup
0x5a336  ldc.i4.0
0x5a337  ldstr    aPrivilegeid_0// "@privilegeid"
0x5a33c  stelem.ref
0x5a33d  dup
0x5a33e  ldc.i4.1
0x5a33f  ldstr    aObjecttypecode_1// "@objecttypecode"
0x5a344  stelem.ref
0x5a345  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5a34a  stloc.1
0x5a34b  ldloc.0
0x5a34c  ldloc.1
0x5a34d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x5a352  ldloc.0
0x5a353  ldc.i4   0x226
0x5a358  ldstr    aAddprivilegeid// "AddPrivilegeIdForObjectTypeCode"
0x5a35d  ldstr    aDA1SSrcCoreObj_6// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x5a362  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x5a367  pop
0x5a368  ldarg.2
0x5a369  ldc.i4.s 0x1F
0x5a36b  ldstr    aCreate// "Create"
0x5a370  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ChangeTrackingHelper::TryAddEntityToChangedTypes(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32, string)
0x5a375  leave.s  loc_5A381
0x5a377  ldloc.0
0x5a378  brfalse.s loc_5A380
0x5a37a  ldloc.0
0x5a37b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a380  endfinally
0x5a381  ret
```
