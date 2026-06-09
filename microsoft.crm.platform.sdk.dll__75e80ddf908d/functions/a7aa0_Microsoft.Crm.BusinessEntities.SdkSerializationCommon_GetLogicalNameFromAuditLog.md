# Microsoft.Crm.BusinessEntities.SdkSerializationCommon::GetLogicalNameFromAuditLog

- ea: `0xa7aa0`
- end: `0xa7b63`
- name: `Microsoft.Crm.BusinessEntities.SdkSerializationCommon::GetLogicalNameFromAuditLog`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xa3230`
- `0xa79d0`

## callees

- `0x6e8e0`
- `0xa7aa0`

## string_xrefs

- `0xa7ac8`: `[Action] = @deleteEntity and [ObjectTypeCode] = @objectTypeCode)`
- `0xa7af4`: `@deleteEntity`

## pseudocode

```c

```

## disassembly

```asm
0xa7aa0  ldarg.0
0xa7aa1  ldc.i4.0
0xa7aa2  ldc.i4.0
0xa7aa3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xa7aa8  stloc.0
0xa7aa9  ldloc.0
0xa7aaa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xa7aaf  ldloc.0
0xa7ab0  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0xa7ab5  stloc.1
0xa7ab6  ldloc.1
0xa7ab7  ldstr    aSelectTop1Chan// "select top 1 changedata from AuditBase "...
0xa7abc  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xa7ac1  ldloc.1
0xa7ac2  dup
0xa7ac3  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0xa7ac8  ldstr    aActionDeleteen// "[Action] = @deleteEntity and [ObjectTyp"...
0xa7acd  call     string [mscorlib]System.String::Concat(string, string)
0xa7ad2  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xa7ad7  ldloc.1
0xa7ad8  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xa7add  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xa7ae2  dup
0xa7ae3  ldstr    aObjecttypecode_1// "@objectTypeCode"
0xa7ae8  ldarg.1
0xa7ae9  box      [mscorlib]System.Int32
0xa7aee  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa7af3  pop
0xa7af4  ldstr    aDeleteentity// "@deleteEntity"
0xa7af9  ldc.i4.s 0x64
0xa7afb  box      [mscorlib]System.Int32
0xa7b00  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa7b05  pop
0xa7b06  ldloc.1
0xa7b07  ldc.i4   0x27D
0xa7b0c  ldstr    aGetlogicalname// "GetLogicalNameFromAuditLog"
0xa7b11  ldstr    aDA1SSrcManaged_14// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0xa7b16  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xa7b1b  stloc.2
0xa7b1c  ldloc.2
0xa7b1d  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xa7b22  brtrue.s loc_A7B30
0xa7b24  ldarg.1
0xa7b25  ldstr    aNotFoundInTheD// "Not Found in the DB."
0xa7b2a  newobj   instance void Microsoft.Crm.Metadata.EntityMetadataNotFoundException::.ctor(int32 entityCode, [opt] string details)
0xa7b2f  throw
0xa7b30  ldloc.2
0xa7b31  ldstr    aChangedata// "changedata"
0xa7b36  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa7b3b  castclass [mscorlib]System.String
0xa7b40  stloc.3
0xa7b41  leave.s  loc_A7B61
0xa7b43  ldloc.2
0xa7b44  brfalse.s loc_A7B4C
0xa7b46  ldloc.2
0xa7b47  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa7b4c  endfinally
0xa7b4d  ldloc.1
0xa7b4e  brfalse.s loc_A7B56
0xa7b50  ldloc.1
0xa7b51  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa7b56  endfinally
0xa7b57  ldloc.0
0xa7b58  brfalse.s loc_A7B60
0xa7b5a  ldloc.0
0xa7b5b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa7b60  endfinally
0xa7b61  ldloc.3
0xa7b62  ret
```
