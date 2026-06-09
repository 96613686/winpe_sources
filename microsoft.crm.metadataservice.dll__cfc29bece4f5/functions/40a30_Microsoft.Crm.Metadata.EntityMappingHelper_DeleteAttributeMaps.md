# Microsoft.Crm.Metadata.EntityMappingHelper::DeleteAttributeMaps

- ea: `0x40a30`
- end: `0x40b1f`
- name: `Microsoft.Crm.Metadata.EntityMappingHelper::DeleteAttributeMaps`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x40a00`

## callees

- `0x40a30`

## string_xrefs

- `0x40a81`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\EntityWrappers.cs`
- `0x40a7c`: `DeleteAttributeMaps`

## pseudocode

```c

```

## disassembly

```asm
0x40a30  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x40a35  stloc.0
0x40a36  ldarg.1
0x40a37  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x40a3c  stloc.1
0x40a3d  ldloc.1
0x40a3e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x40a43  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x40a48  ldloc.1
0x40a49  ldstr    aSelectAttribut_1// "\r\n\t\t\t\t\tselect AttributeMapId fro"...
0x40a4e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x40a53  dup
0x40a54  ldstr    aSourceentityna_1// "@sourceentityname"
0x40a59  ldarg.0
0x40a5a  ldfld    string EntityMapping::SourceName
0x40a5f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x40a64  pop
0x40a65  ldstr    aTargetentityna_1// "@targetentityname"
0x40a6a  ldarg.0
0x40a6b  ldfld    string EntityMapping::TargetName
0x40a70  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x40a75  pop
0x40a76  ldloc.1
0x40a77  ldc.i4   0x7A7
0x40a7c  ldstr    aDeleteattribut_0// "DeleteAttributeMaps"
0x40a81  ldstr    aDA1SSrcCoreObj_4// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x40a86  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x40a8b  stloc.2
0x40a8c  br.s     loc_40AA4
0x40a8e  ldloc.0
0x40a8f  ldloc.2
0x40a90  ldstr    aAttributemapid_0// "AttributeMapId"
0x40a95  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x40a9a  unbox.any [mscorlib]System.Guid
0x40a9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x40aa4  ldloc.2
0x40aa5  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x40aaa  brtrue.s loc_40A8E
0x40aac  leave.s  loc_40AC2
0x40aae  ldloc.2
0x40aaf  brfalse.s loc_40AB7
0x40ab1  ldloc.2
0x40ab2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40ab7  endfinally
0x40ab8  ldloc.1
0x40ab9  brfalse.s loc_40AC1
0x40abb  ldloc.1
0x40abc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40ac1  endfinally
0x40ac2  ldloc.0
0x40ac3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x40ac8  ldc.i4.0
0x40ac9  ble.s    loc_40B1E
0x40acb  ldloc.0
0x40acc  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x40ad1  stloc.3
0x40ad2  br.s     loc_40B05
0x40ad4  ldloca.s 3
0x40ad6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x40adb  stloc.s  4
0x40add  ldc.i4   0x11F9
0x40ae2  ldarg.1
0x40ae3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x40ae8  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(int32, valuetype [mscorlib]System.Guid)
0x40aed  ldloc.s  4
0x40aef  ldstr    aAttributemap// "AttributeMap"
0x40af4  ldarg.1
0x40af5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x40afa  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x40aff  ldarg.1
0x40b00  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x40b05  ldloca.s 3
0x40b07  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x40b0c  brtrue.s loc_40AD4
0x40b0e  leave.s  loc_40B1E
0x40b10  ldloca.s 3
0x40b12  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x40b18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40b1d  endfinally
0x40b1e  ret
```
