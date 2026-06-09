# Microsoft.Crm.Metadata.EntityService::DeleteOfflineFilters

- ea: `0x373a0`
- end: `0x3742a`
- name: `Microsoft.Crm.Metadata.EntityService::DeleteOfflineFilters`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x36c60`

## callees

- `0x373a0`

## string_xrefs

- `0x373ee`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\EntityService.cs`
- `0x373d6`: `delete from UserQueryBase Where ReturnedTypeCode = @returnedtypecode and QueryType = @querytype`
- `0x373e9`: `DeleteOfflineFilters`

## pseudocode

```c

```

## disassembly

```asm
0x373a0  ldarg.1
0x373a1  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x373a6  stloc.0
0x373a7  ldloc.0
0x373a8  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x373ad  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x373b2  dup
0x373b3  ldstr    aReturnedtypeco_0// "@returnedtypecode"
0x373b8  ldarg.0
0x373b9  box      [mscorlib]System.Int32
0x373be  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x373c3  pop
0x373c4  ldstr    aQuerytype_0// "@querytype"
0x373c9  ldc.i4.s 0x10
0x373cb  box      [mscorlib]System.Int32
0x373d0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x373d5  pop
0x373d6  ldstr    aDeleteFromUser_1// "delete from UserQueryBase Where Returne"...
0x373db  stloc.1
0x373dc  ldloc.0
0x373dd  ldloc.1
0x373de  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x373e3  ldloc.0
0x373e4  ldc.i4   0x1706
0x373e9  ldstr    aDeleteofflinef// "DeleteOfflineFilters"
0x373ee  ldstr    aDA1SSrcCoreObj_3// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x373f3  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x373f8  pop
0x373f9  leave.s  loc_37429
0x373fb  stloc.2
0x373fc  ldloc.2
0x373fd  ldarg.1
0x373fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x37403  ldc.i4.s 0x19
0x37405  ldstr    aExceptionWhenE_0// "Exception when executing non-query: {0}"...
0x3740a  ldc.i4.2
0x3740b  newarr   [mscorlib]System.Object
0x37410  dup
0x37411  ldc.i4.0
0x37412  ldloc.0
0x37413  stelem.ref
0x37414  dup
0x37415  ldc.i4.1
0x37416  ldloc.2
0x37417  stelem.ref
0x37418  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3741d  rethrow
0x3741f  ldloc.0
0x37420  brfalse.s loc_37428
0x37422  ldloc.0
0x37423  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37428  endfinally
0x37429  ret
```
