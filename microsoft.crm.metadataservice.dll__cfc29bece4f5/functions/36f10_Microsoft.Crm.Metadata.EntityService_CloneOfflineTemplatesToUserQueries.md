# Microsoft.Crm.Metadata.EntityService::CloneOfflineTemplatesToUserQueries

- ea: `0x36f10`
- end: `0x37063`
- name: `Microsoft.Crm.Metadata.EntityService::CloneOfflineTemplatesToUserQueries`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x36bb0`

## callees

- `0x36f10`

## string_xrefs

- `0x37026`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\EntityService.cs`
- `0x36f63`: `@fetchxml`
- `0x36f71`: `@columnsetxml`
- `0x36f82`: `@layoutxml`
- `0x36fb6`: `@createdby`
- `0x36ffd`: `@templateid`
- `0x3700e`: `insert into UserQueryBase\n				(UserQueryId, Name, Description, ReturnedTypeCode, QueryType, FetchXml,\n					ColumnSetXml, LayoutXml, OwningBusinessUnit, ModifiedBy, ModifiedOn, CreatedBy, CreatedOn,\n					StatusCode, StateCode, OwnerId, ParentQueryId)\n				select newid(),@name, @description, @returnedtypecode, @querytype, @fetchxml,\n					@columnsetxml, @layoutxml, u.BusinessUnitId, @modifiedby, getutcdate(), @createdby, getutcdate(),\n					@statuscode, @statecode, u.SystemUserId, @templa`
- `0x37021`: `CloneOfflineTemplatesToUserQueries`

## pseudocode

```c

```

## disassembly

```asm
0x36f10  ldarg.s  5
0x36f12  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x36f17  stloc.0
0x36f18  ldloc.0
0x36f19  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x36f1e  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x36f23  dup
0x36f24  ldstr    aName_1// "@name"
0x36f29  ldarg.2
0x36f2a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36f2f  pop
0x36f30  dup
0x36f31  ldstr    aDescription_1// "@description"
0x36f36  ldarg.3
0x36f37  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36f3c  pop
0x36f3d  dup
0x36f3e  ldstr    aReturnedtypeco_0// "@returnedtypecode"
0x36f43  ldarg.0
0x36f44  box      [mscorlib]System.Int32
0x36f49  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36f4e  pop
0x36f4f  dup
0x36f50  ldstr    aQuerytype_0// "@querytype"
0x36f55  ldc.i4.s 0x10
0x36f57  box      [mscorlib]System.Int32
0x36f5c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36f61  pop
0x36f62  dup
0x36f63  ldstr    aFetchxml_0// "@fetchxml"
0x36f68  ldarg.s  4
0x36f6a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36f6f  pop
0x36f70  dup
0x36f71  ldstr    aColumnsetxml// "@columnsetxml"
0x36f76  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x36f7b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36f80  pop
0x36f81  dup
0x36f82  ldstr    aLayoutxml// "@layoutxml"
0x36f87  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x36f8c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36f91  pop
0x36f92  dup
0x36f93  ldstr    aStatuscode_1// "@statuscode"
0x36f98  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x36f9d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36fa2  pop
0x36fa3  dup
0x36fa4  ldstr    aStatecode_2// "@statecode"
0x36fa9  ldc.i4.0
0x36faa  box      [mscorlib]System.Int32
0x36faf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36fb4  pop
0x36fb5  dup
0x36fb6  ldstr    aCreatedby_2// "@createdby"
0x36fbb  ldarg.s  5
0x36fbd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x36fc2  box      [mscorlib]System.Guid
0x36fc7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36fcc  pop
0x36fcd  dup
0x36fce  ldstr    aModifiedby_1// "@modifiedby"
0x36fd3  ldarg.s  5
0x36fd5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x36fda  box      [mscorlib]System.Guid
0x36fdf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36fe4  pop
0x36fe5  dup
0x36fe6  ldstr    aOrganizationid_0// "@organizationid"
0x36feb  ldarg.s  5
0x36fed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x36ff2  box      [mscorlib]System.Guid
0x36ff7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36ffc  pop
0x36ffd  ldstr    aTemplateid// "@templateid"
0x37002  ldarg.1
0x37003  box      [mscorlib]System.Guid
0x37008  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3700d  pop
0x3700e  ldstr    aInsertIntoUser// "insert into UserQueryBase\r\n\t\t\t\t(U"...
0x37013  stloc.1
0x37014  ldloc.0
0x37015  ldloc.1
0x37016  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3701b  ldloc.0
0x3701c  ldc.i4   0x1688
0x37021  ldstr    aCloneofflinete// "CloneOfflineTemplatesToUserQueries"
0x37026  ldstr    aDA1SSrcCoreObj_3// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x3702b  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x37030  pop
0x37031  leave.s  loc_37062
0x37033  stloc.2
0x37034  ldloc.2
0x37035  ldarg.s  5
0x37037  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3703c  ldc.i4.s 0x19
0x3703e  ldstr    aExceptionWhenE_0// "Exception when executing non-query: {0}"...
0x37043  ldc.i4.2
0x37044  newarr   [mscorlib]System.Object
0x37049  dup
0x3704a  ldc.i4.0
0x3704b  ldloc.0
0x3704c  stelem.ref
0x3704d  dup
0x3704e  ldc.i4.1
0x3704f  ldloc.2
0x37050  stelem.ref
0x37051  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37056  rethrow
0x37058  ldloc.0
0x37059  brfalse.s loc_37061
0x3705b  ldloc.0
0x3705c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37061  endfinally
0x37062  ret
```
