# Microsoft.Crm.Asynchronous.DataManagementDataAccessBase::CreateAsyncOperation

- ea: `0x3a30`
- end: `0x3b61`
- name: `Microsoft.Crm.Asynchronous.DataManagementDataAccessBase::CreateAsyncOperation`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x3a30`

## string_xrefs

- `0x3a37`: `if not exists(SELECT 1 from AsyncOperationBase WHERE RequestId = @requestId and RegardingObjectId = @regardingObjectId and OperationType = @operationType and Data = @data)\ninsert into AsyncOperationBase\n(\n\n	[RegardingObjectId],\n	[RegardingObjectTypeCode],\n	[DependencyToken],\n	[ModifiedBy],\n	[OwningBusinessUnit],\n	[CreatedOn],	\n	[StateCode],\n	[Data],\n	[AsyncOperationId],\n	[OperationType],\n	[ModifiedOn],\n	[CreatedBy],\n	[OwnerId],\n	[Name],\n	[Depth],\n	[Correlati`
- `0x3ae3`: `@dependencytoken`
- `0x3b1a`: `@dependencytoken`

## pseudocode

```c

```

## disassembly

```asm
0x3a30  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x3a35  stloc.0
0x3a36  ldloc.0
0x3a37  ldstr    aIfNotExistsSel_2// "if not exists(SELECT 1 from AsyncOperat"...
0x3a3c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3a41  ldloc.0
0x3a42  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3a47  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3a4c  stloc.1
0x3a4d  ldloc.1
0x3a4e  ldstr    aId// "@id"
0x3a53  ldarg.1
0x3a54  box      [mscorlib]System.Guid
0x3a59  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3a5e  pop
0x3a5f  ldloc.1
0x3a60  ldstr    aData// "@data"
0x3a65  ldarg.2
0x3a66  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3a6b  pop
0x3a6c  ldloc.1
0x3a6d  ldstr    aRegardingobjec// "@regardingObjectId"
0x3a72  ldarga.s 3
0x3a74  ldstr    aD_0// "D"
0x3a79  call     instance string [mscorlib]System.Guid::ToString(string)
0x3a7e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3a83  pop
0x3a84  ldloc.1
0x3a85  ldstr    aOperationtype_0// "@operationType"
0x3a8a  ldarg.s  5
0x3a8c  box      [mscorlib]System.Int32
0x3a91  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3a96  pop
0x3a97  ldloc.1
0x3a98  ldstr    aRequestid_0// "@requestId"
0x3a9d  ldarga.s 6
0x3a9f  ldstr    aD_0// "D"
0x3aa4  call     instance string [mscorlib]System.Guid::ToString(string)
0x3aa9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3aae  pop
0x3aaf  ldloc.1
0x3ab0  ldstr    aRegardingobjec_0// "@regardingObjectTypeCode"
0x3ab5  ldarg.s  7
0x3ab7  box      [mscorlib]System.Int32
0x3abc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3ac1  pop
0x3ac2  ldloc.1
0x3ac3  ldstr    aModifiedon// "@modifiedOn"
0x3ac8  ldarg.0
0x3ac9  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x3ace  box      [mscorlib]System.DateTime
0x3ad3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3ad8  pop
0x3ad9  ldarg.s  4
0x3adb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3ae0  brfalse.s loc_3B19
0x3ae2  ldloc.1
0x3ae3  ldstr    aDependencytoke// "@dependencytoken"
0x3ae8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x3aed  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3af2  pop
0x3af3  ldloc.1
0x3af4  ldstr    aStatecode_0// "@stateCode"
0x3af9  ldc.i4.0
0x3afa  box      [mscorlib]System.Int32
0x3aff  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3b04  pop
0x3b05  ldloc.1
0x3b06  ldstr    aStatuscode_0// "@statusCode"
0x3b0b  ldc.i4.0
0x3b0c  box      [mscorlib]System.Int32
0x3b11  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3b16  pop
0x3b17  br.s     loc_3B4C
0x3b19  ldloc.1
0x3b1a  ldstr    aDependencytoke// "@dependencytoken"
0x3b1f  ldarg.s  4
0x3b21  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3b26  pop
0x3b27  ldloc.1
0x3b28  ldstr    aStatecode_0// "@stateCode"
0x3b2d  ldc.i4.1
0x3b2e  box      [mscorlib]System.Int32
0x3b33  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3b38  pop
0x3b39  ldloc.1
0x3b3a  ldstr    aStatuscode_0// "@statusCode"
0x3b3f  ldc.i4.s 0xA
0x3b41  box      [mscorlib]System.Int32
0x3b46  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3b4b  pop
0x3b4c  ldarg.0
0x3b4d  ldloc.0
0x3b4e  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x3b53  pop
0x3b54  leave.s  loc_3B60
0x3b56  ldloc.0
0x3b57  brfalse.s loc_3B5F
0x3b59  ldloc.0
0x3b5a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3b5f  endfinally
0x3b60  ret
```
