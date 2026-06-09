# Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataSyncHelper::RemoveEntryFromTrackingDeletedObjects

- ea: `0x4c890`
- end: `0x4c8f0`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataSyncHelper::RemoveEntryFromTrackingDeletedObjects`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x4c750`

## callees

- `0x4c890`

## string_xrefs

- `0x4c898`: `delete from [MetadataSyncTrackingDeletedObject] where [ObjectId] = @ObjectId and [MetadataObjectTypeCode] = @MetadataObjectTypeCode`
- `0x4c8d3`: `RemoveEntryFromTrackingDeletedObjects`

## pseudocode

```c

```

## disassembly

```asm
0x4c890  ldarg.2
0x4c891  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand()
0x4c896  stloc.0
0x4c897  ldloc.0
0x4c898  ldstr    aDeleteFromMeta// "delete from [MetadataSyncTrackingDelete"...
0x4c89d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x4c8a2  ldloc.0
0x4c8a3  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4c8a8  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x4c8ad  dup
0x4c8ae  ldstr    aObjectid_3// "@ObjectId"
0x4c8b3  ldarg.1
0x4c8b4  box      [mscorlib]System.Guid
0x4c8b9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4c8be  pop
0x4c8bf  ldstr    aMetadataobject_9// "@MetadataObjectTypeCode"
0x4c8c4  ldarg.0
0x4c8c5  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataObjectTypeCode
0x4c8ca  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4c8cf  pop
0x4c8d0  ldloc.0
0x4c8d1  ldc.i4.s 0x72
0x4c8d3  ldstr    aRemoveentryfro// "RemoveEntryFromTrackingDeletedObjects"
0x4c8d8  ldstr    aDA1SSrcManaged_10// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x4c8dd  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x4c8e2  pop
0x4c8e3  leave.s  loc_4C8EF
0x4c8e5  ldloc.0
0x4c8e6  brfalse.s loc_4C8EE
0x4c8e8  ldloc.0
0x4c8e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c8ee  endfinally
0x4c8ef  ret
```
