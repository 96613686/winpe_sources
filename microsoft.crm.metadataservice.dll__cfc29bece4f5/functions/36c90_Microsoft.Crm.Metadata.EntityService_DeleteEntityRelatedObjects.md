# Microsoft.Crm.Metadata.EntityService::DeleteEntityRelatedObjects

- ea: `0x36c90`
- end: `0x36d2a`
- name: `Microsoft.Crm.Metadata.EntityService::DeleteEntityRelatedObjects`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x31b10`

## callees

- `0x36c90`

## string_xrefs

- `0x36cb3`: `delete from [UserEntityUISettingsBase] where ObjectTypeCode = @objecttypecode`
- `0x36cb9`: `delete from [UserEntityInstanceDataBase] where ObjectTypeCode = @objecttypecode`
- `0x36ccc`: `DeleteEntityRelatedObjects`
- `0x36ce9`: `DeleteEntityRelatedObjects`
- `0x36cd1`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\EntityService.cs`
- `0x36cee`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\EntityService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x36c90  ldarg.2
0x36c91  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x36c96  stloc.0
0x36c97  ldloc.0
0x36c98  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x36c9d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x36ca2  ldstr    aObjecttypecode_1// "@objecttypecode"
0x36ca7  ldarg.1
0x36ca8  box      [mscorlib]System.Int32
0x36cad  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36cb2  pop
0x36cb3  ldstr    aDeleteFromUser// "delete from [UserEntityUISettingsBase] "...
0x36cb8  stloc.1
0x36cb9  ldstr    aDeleteFromUser_0// "delete from [UserEntityInstanceDataBase"...
0x36cbe  stloc.2
0x36cbf  ldloc.0
0x36cc0  ldloc.1
0x36cc1  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x36cc6  ldloc.0
0x36cc7  ldc.i4   0x1610
0x36ccc  ldstr    aDeleteentityre// "DeleteEntityRelatedObjects"
0x36cd1  ldstr    aDA1SSrcCoreObj_3// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x36cd6  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x36cdb  pop
0x36cdc  ldloc.0
0x36cdd  ldloc.2
0x36cde  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x36ce3  ldloc.0
0x36ce4  ldc.i4   0x1612
0x36ce9  ldstr    aDeleteentityre// "DeleteEntityRelatedObjects"
0x36cee  ldstr    aDA1SSrcCoreObj_3// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x36cf3  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x36cf8  pop
0x36cf9  leave.s  loc_36D29
0x36cfb  stloc.3
0x36cfc  ldloc.3
0x36cfd  ldarg.2
0x36cfe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x36d03  ldc.i4.s 0x19
0x36d05  ldstr    aExceptionWhenE_0// "Exception when executing non-query: {0}"...
0x36d0a  ldc.i4.2
0x36d0b  newarr   [mscorlib]System.Object
0x36d10  dup
0x36d11  ldc.i4.0
0x36d12  ldloc.0
0x36d13  stelem.ref
0x36d14  dup
0x36d15  ldc.i4.1
0x36d16  ldloc.3
0x36d17  stelem.ref
0x36d18  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x36d1d  rethrow
0x36d1f  ldloc.0
0x36d20  brfalse.s loc_36D28
0x36d22  ldloc.0
0x36d23  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36d28  endfinally
0x36d29  ret
```
