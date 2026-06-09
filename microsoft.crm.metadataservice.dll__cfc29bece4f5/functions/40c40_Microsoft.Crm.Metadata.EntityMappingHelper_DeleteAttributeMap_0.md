# Microsoft.Crm.Metadata.EntityMappingHelper::DeleteAttributeMap_0

- ea: `0x40c40`
- end: `0x40d29`
- name: `Microsoft.Crm.Metadata.EntityMappingHelper::DeleteAttributeMap_0`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x40b80`
- `0x40c40`

## callees

- `0x40c40`

## string_xrefs

- `0x40c7f`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\EntityWrappers.cs`
- `0x40c7a`: `DeleteAttributeMap`

## pseudocode

```c

```

## disassembly

```asm
0x40c40  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x40c45  stloc.0
0x40c46  ldarg.1
0x40c47  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x40c4c  stloc.2
0x40c4d  ldloc.2
0x40c4e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x40c53  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x40c58  ldloc.2
0x40c59  ldstr    aSelectAttribut_3// "select AttributeMapId from AttributeMap"...
0x40c5e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x40c63  ldstr    aParentattribut_0// "@parentattributemapid"
0x40c68  ldarg.0
0x40c69  box      [mscorlib]System.Guid
0x40c6e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x40c73  pop
0x40c74  ldloc.2
0x40c75  ldc.i4   0x7FC
0x40c7a  ldstr    aDeleteattribut_1// "DeleteAttributeMap"
0x40c7f  ldstr    aDA1SSrcCoreObj_4// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x40c84  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x40c89  stloc.3
0x40c8a  br.s     loc_40CA2
0x40c8c  ldloc.0
0x40c8d  ldloc.3
0x40c8e  ldstr    aAttributemapid_0// "AttributeMapId"
0x40c93  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x40c98  unbox.any [mscorlib]System.Guid
0x40c9d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x40ca2  ldloc.3
0x40ca3  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x40ca8  brtrue.s loc_40C8C
0x40caa  leave.s  loc_40CC0
0x40cac  ldloc.3
0x40cad  brfalse.s loc_40CB5
0x40caf  ldloc.3
0x40cb0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40cb5  endfinally
0x40cb6  ldloc.2
0x40cb7  brfalse.s loc_40CBF
0x40cb9  ldloc.2
0x40cba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40cbf  endfinally
0x40cc0  ldloc.0
0x40cc1  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x40cc6  stloc.s  4
0x40cc8  br.s     loc_40CD7
0x40cca  ldloca.s 4
0x40ccc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x40cd1  ldarg.1
0x40cd2  call     void Microsoft.Crm.Metadata.EntityMappingHelper::DeleteAttributeMap(valuetype [mscorlib]System.Guid attributeMapId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x40cd7  ldloca.s 4
0x40cd9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x40cde  brtrue.s loc_40CCA
0x40ce0  leave.s  loc_40CF0
0x40ce2  ldloca.s 4
0x40ce4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x40cea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40cef  endfinally
0x40cf0  ldstr    aAttributemap// "AttributeMap"
0x40cf5  ldarg.1
0x40cf6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x40cfb  stloc.1
0x40cfc  ldloc.1
0x40cfd  ldstr    aAttributemapid// "attributemapid"
0x40d02  ldc.i4.0
0x40d03  ldarg.0
0x40d04  box      [mscorlib]System.Guid
0x40d09  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x40d0e  pop
0x40d0f  ldloc.1
0x40d10  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x40d15  ldloc.1
0x40d16  ldc.i4.0
0x40d17  ldarg.1
0x40d18  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::DeleteUsingDeletePlan(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x40d1d  pop
0x40d1e  ldarg.1
0x40d1f  ldc.i4.2
0x40d20  ldarg.0
0x40d21  ldc.i4.s 0x2F
0x40d23  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x40d28  ret
```
