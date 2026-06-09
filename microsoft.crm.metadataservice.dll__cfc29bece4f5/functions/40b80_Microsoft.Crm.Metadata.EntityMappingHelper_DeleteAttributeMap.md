# Microsoft.Crm.Metadata.EntityMappingHelper::DeleteAttributeMap

- ea: `0x40b80`
- end: `0x40c33`
- name: `Microsoft.Crm.Metadata.EntityMappingHelper::DeleteAttributeMap`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x54ee0`

## callees

- `0x40b80`
- `0x40c40`

## string_xrefs

- `0x40bd9`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\EntityWrappers.cs`
- `0x40bd4`: `DeleteAttributeMap`

## pseudocode

```c

```

## disassembly

```asm
0x40b80  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40b85  stloc.0
0x40b86  ldarg.3
0x40b87  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x40b8c  stloc.1
0x40b8d  ldloc.1
0x40b8e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x40b93  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x40b98  ldloc.1
0x40b99  ldstr    aSelectAttribut_2// "select AttributeMapId from AttributeMap"...
0x40b9e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x40ba3  dup
0x40ba4  ldstr    aSourceattribut_1// "@sourceattributename"
0x40ba9  ldarg.1
0x40baa  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x40baf  pop
0x40bb0  dup
0x40bb1  ldstr    aTargetattribut_1// "@targetattributename"
0x40bb6  ldarg.2
0x40bb7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x40bbc  pop
0x40bbd  ldstr    aEntitymapid_1// "@entitymapid"
0x40bc2  ldarg.0
0x40bc3  box      [mscorlib]System.Guid
0x40bc8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x40bcd  pop
0x40bce  ldloc.1
0x40bcf  ldc.i4   0x7DD
0x40bd4  ldstr    aDeleteattribut_1// "DeleteAttributeMap"
0x40bd9  ldstr    aDA1SSrcCoreObj_4// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x40bde  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x40be3  stloc.2
0x40be4  ldloc.2
0x40be5  brfalse.s loc_40BEE
0x40be7  ldloc.2
0x40be8  unbox.any [mscorlib]System.Guid
0x40bed  stloc.0
0x40bee  leave.s  loc_40C1E
0x40bf0  stloc.3
0x40bf1  ldloc.3
0x40bf2  ldarg.3
0x40bf3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x40bf8  ldc.i4.s 0x19
0x40bfa  ldstr    aExceptionWhenE_1// "Exception when executing scalar: {0} Ex"...
0x40bff  ldc.i4.2
0x40c00  newarr   [mscorlib]System.Object
0x40c05  dup
0x40c06  ldc.i4.0
0x40c07  ldloc.1
0x40c08  stelem.ref
0x40c09  dup
0x40c0a  ldc.i4.1
0x40c0b  ldloc.3
0x40c0c  stelem.ref
0x40c0d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x40c12  rethrow
0x40c14  ldloc.1
0x40c15  brfalse.s loc_40C1D
0x40c17  ldloc.1
0x40c18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40c1d  endfinally
0x40c1e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40c23  ldloc.0
0x40c24  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x40c29  brfalse.s loc_40C32
0x40c2b  ldloc.0
0x40c2c  ldarg.3
0x40c2d  call     void Microsoft.Crm.Metadata.EntityMappingHelper::DeleteAttributeMap(valuetype [mscorlib]System.Guid attributeMapId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x40c32  ret
```
