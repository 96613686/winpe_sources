# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::IsEntityAndAttributeAlreadyProcessed

- ea: `0x3a60`
- end: `0x3b52`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::IsEntityAndAttributeAlreadyProcessed`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x36b0`

## callees

- `0x3a60`

## string_xrefs

- `0x3aeb`: `IsEntityAndAttributeAlreadyProcessed`

## pseudocode

```c

```

## disassembly

```asm
0x3a60  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::.ctor()
0x3a65  stloc.0
0x3a66  ldarg.s  4
0x3a68  ldc.i4.0
0x3a69  stind.i4
0x3a6a  ldstr    aSelectStatusFr// "SELECT [Status] FROM [dbo].[DateTimeCon"...
0x3a6f  stloc.1
0x3a70  ldstr    aAttributeid// "AttributeId"
0x3a75  stloc.2
0x3a76  ldloc.0
0x3a77  ldloc.2
0x3a78  ldarg.2
0x3a79  box      [mscorlib]System.Guid
0x3a7e  ldc.i4.s 0xE
0x3a80  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, valuetype [System.Data]System.Data.SqlDbType)
0x3a85  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0x3a8a  stloc.3
0x3a8b  ldstr    aEntityid// "EntityId"
0x3a90  stloc.s  4
0x3a92  ldloc.0
0x3a93  ldloc.s  4
0x3a95  ldarg.1
0x3a96  box      [mscorlib]System.Guid
0x3a9b  ldc.i4.s 0xE
0x3a9d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, valuetype [System.Data]System.Data.SqlDbType)
0x3aa2  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0x3aa7  stloc.s  5
0x3aa9  ldarg.3
0x3aaa  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x3aaf  stloc.s  6
0x3ab1  ldloc.0
0x3ab2  ldloc.s  6
0x3ab4  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3ab9  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3abe  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParametersToSqlParameterCollection(class [System.Data]System.Data.SqlClient.SqlParameterCollection)
0x3ac3  ldloc.s  6
0x3ac5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3aca  ldloc.1
0x3acb  ldc.i4.2
0x3acc  newarr   [mscorlib]System.Object
0x3ad1  dup
0x3ad2  ldc.i4.0
0x3ad3  ldloc.s  5
0x3ad5  stelem.ref
0x3ad6  dup
0x3ad7  ldc.i4.1
0x3ad8  ldloc.3
0x3ad9  stelem.ref
0x3ada  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3adf  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3ae4  ldloc.s  6
0x3ae6  ldc.i4   0x465
0x3aeb  ldstr    aIsentityandatt// "IsEntityAndAttributeAlreadyProcessed"
0x3af0  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x3af5  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x3afa  stloc.s  7
0x3afc  ldloc.s  7
0x3afe  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x3b03  brfalse.s loc_3B32
0x3b05  ldarg.s  4
0x3b07  ldloc.s  7
0x3b09  ldstr    aStatus// "Status"
0x3b0e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3b13  unbox.any [mscorlib]System.Int32
0x3b18  stind.i4
0x3b19  ldloc.s  7
0x3b1b  ldstr    aStatus// "Status"
0x3b20  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3b25  unbox.any [mscorlib]System.Int32
0x3b2a  ldc.i4.1
0x3b2b  bne.un.s loc_3B32
0x3b2d  ldc.i4.1
0x3b2e  stloc.s  8
0x3b30  leave.s  loc_3B4F
0x3b32  ldc.i4.0
0x3b33  stloc.s  8
0x3b35  leave.s  loc_3B4F
0x3b37  ldloc.s  7
0x3b39  brfalse.s loc_3B42
0x3b3b  ldloc.s  7
0x3b3d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3b42  endfinally
0x3b43  ldloc.s  6
0x3b45  brfalse.s loc_3B4E
0x3b47  ldloc.s  6
0x3b49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3b4e  endfinally
0x3b4f  ldloc.s  8
0x3b51  ret
```
