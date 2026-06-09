# Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::GetDeletedMetadata

- ea: `0xeb10`
- end: `0xebf6`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::GetDeletedMetadata`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xe8c0`

## callees

- `0xeb10`
- `0xec00`
- `0x15ca0`
- `0x15db0`

## string_xrefs

- `0xeb26`: `select distinct x.ObjectId, x.MetadataObjectTypeCode from MetadataSyncTrackingDeletedObject x where x.Timestamp > CONVERT(rowversion, @Timestamp)`
- `0xeb58`: `GetDeletedMetadata`
- `0xeb5d`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SDK\MetadataServiceProvider.cs`

## pseudocode

```c

```

## disassembly

```asm
0xeb10  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataCollection::.ctor()
0xeb15  stloc.0
0xeb16  ldarg.1
0xeb17  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Sdk.Metadata.MetadataConversionContext::get_OrganizationContext()
0xeb1c  castclass [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext
0xeb21  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xeb26  ldstr    aSelectDistinct// "select distinct x.ObjectId, x.MetadataO"...
0xeb2b  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0xeb30  stloc.1
0xeb31  ldloc.1
0xeb32  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xeb37  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xeb3c  ldstr    aTimestamp// "@Timestamp"
0xeb41  ldarg.1
0xeb42  callvirt instance int64 Microsoft.Crm.Sdk.Metadata.MetadataConversionContext::get_ClientVersionNumber()
0xeb47  box      [mscorlib]System.Int64
0xeb4c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xeb51  pop
0xeb52  ldloc.1
0xeb53  ldc.i4   0x326
0xeb58  ldstr    aGetdeletedmeta// "GetDeletedMetadata"
0xeb5d  ldstr    aDA1SSrcCoreObj_0// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0xeb62  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xeb67  stloc.2
0xeb68  br.s     loc_EBD6
0xeb6a  ldloc.2
0xeb6b  ldstr    aObjectid_0// "ObjectId"
0xeb70  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xeb75  unbox.any [mscorlib]System.Guid
0xeb7a  stloc.3
0xeb7b  ldloc.2
0xeb7c  ldstr    aMetadataobject// "MetadataObjectTypeCode"
0xeb81  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xeb86  unbox.any [mscorlib]System.Int32
0xeb8b  stloc.s  4
0xeb8d  ldarg.0
0xeb8e  ldloc.s  4
0xeb90  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataFilters> Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::GetDeletedMetadataFilter(int32 metadataObjectTypeCode)
0xeb95  stloc.s  6
0xeb97  ldloca.s 6
0xeb99  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataFilters>::get_HasValue()
0xeb9e  brfalse.s loc_EBD6
0xeba0  ldloca.s 6
0xeba2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataFilters>::get_Value()
0xeba7  stloc.s  7
0xeba9  ldloc.s  7
0xebab  ldarg.2
0xebac  and
0xebad  ldloc.s  7
0xebaf  bne.un.s loc_EBD6
0xebb1  ldloc.0
0xebb2  ldloc.s  7
0xebb4  ldloca.s 5
0xebb6  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataFilters, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<valuetype [mscorlib]System.Guid>>::TryGetValue(var<u1>, !!T0)
0xebbb  brtrue.s loc_EBCE
0xebbd  newobj   instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<valuetype [mscorlib]System.Guid>::.ctor()
0xebc2  stloc.s  5
0xebc4  ldloc.0
0xebc5  ldloc.s  7
0xebc7  ldloc.s  5
0xebc9  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.DeletedMetadataFilters, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<valuetype [mscorlib]System.Guid>>::Add(var<u1>, !!T0)
0xebce  ldloc.s  5
0xebd0  ldloc.3
0xebd1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xebd6  ldloc.2
0xebd7  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xebdc  brtrue.s loc_EB6A
0xebde  leave.s  loc_EBF4
0xebe0  ldloc.2
0xebe1  brfalse.s loc_EBE9
0xebe3  ldloc.2
0xebe4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xebe9  endfinally
0xebea  ldloc.1
0xebeb  brfalse.s loc_EBF3
0xebed  ldloc.1
0xebee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xebf3  endfinally
0xebf4  ldloc.0
0xebf5  ret
```
