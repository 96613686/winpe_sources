# Microsoft.Crm.BusinessEntities.SdkSerializationCommon::GetObjectTypeCodeFromAuditLog

- ea: `0xa7b70`
- end: `0xa7c2e`
- name: `Microsoft.Crm.BusinessEntities.SdkSerializationCommon::GetObjectTypeCodeFromAuditLog`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xa3270`
- `0xa7980`

## callees

- `0x6e890`
- `0xa7b70`

## string_xrefs

- `0xa7bbf`: `@deleteEntity`
- `0xa7b98`: `[Action] = @deleteEntity and [ChangeData] = @logicalName)`

## pseudocode

```c

```

## disassembly

```asm
0xa7b70  ldarg.0
0xa7b71  ldc.i4.0
0xa7b72  ldc.i4.0
0xa7b73  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa7b78  stloc.0
0xa7b79  ldloc.0
0xa7b7a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xa7b7f  ldloc.0
0xa7b80  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0xa7b85  stloc.1
0xa7b86  ldloc.1
0xa7b87  ldstr    aSelectTop1Obje// "select top 1 ObjectTypeCode from AuditB"...
0xa7b8c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xa7b91  ldloc.1
0xa7b92  dup
0xa7b93  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0xa7b98  ldstr    aActionDeleteen_0// "[Action] = @deleteEntity and [ChangeDat"...
0xa7b9d  call     string [mscorlib]System.String::Concat(string, string)
0xa7ba2  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xa7ba7  ldloc.1
0xa7ba8  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xa7bad  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xa7bb2  dup
0xa7bb3  ldstr    aLogicalname_1// "@logicalName"
0xa7bb8  ldarg.1
0xa7bb9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa7bbe  pop
0xa7bbf  ldstr    aDeleteentity// "@deleteEntity"
0xa7bc4  ldc.i4.s 0x64
0xa7bc6  box      [mscorlib]System.Int32
0xa7bcb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa7bd0  pop
0xa7bd1  ldloc.1
0xa7bd2  ldc.i4   0x298
0xa7bd7  ldstr    aGetobjecttypec// "GetObjectTypeCodeFromAuditLog"
0xa7bdc  ldstr    aDA1SSrcManaged_14// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0xa7be1  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xa7be6  stloc.2
0xa7be7  ldloc.2
0xa7be8  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xa7bed  brtrue.s loc_A7BFB
0xa7bef  ldarg.1
0xa7bf0  ldstr    aNotFoundInTheD// "Not Found in the DB."
0xa7bf5  newobj   instance void Microsoft.Crm.Metadata.EntityMetadataNotFoundException::.ctor(string entityName, [opt] string details)
0xa7bfa  throw
0xa7bfb  ldloc.2
0xa7bfc  ldstr    aObjecttypecode_0// "objecttypecode"
0xa7c01  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa7c06  unbox.any [mscorlib]System.Int32
0xa7c0b  stloc.3
0xa7c0c  leave.s  loc_A7C2C
0xa7c0e  ldloc.2
0xa7c0f  brfalse.s loc_A7C17
0xa7c11  ldloc.2
0xa7c12  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa7c17  endfinally
0xa7c18  ldloc.1
0xa7c19  brfalse.s loc_A7C21
0xa7c1b  ldloc.1
0xa7c1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa7c21  endfinally
0xa7c22  ldloc.0
0xa7c23  brfalse.s loc_A7C2B
0xa7c25  ldloc.0
0xa7c26  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa7c2b  endfinally
0xa7c2c  ldloc.3
0xa7c2d  ret
```
