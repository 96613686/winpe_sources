# Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::Retrieve

- ea: `0x6dbd0`
- end: `0x6dcd8`
- name: `Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::Retrieve`
- size: `264`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x578f0`
- `0x743a0`
- `0x8ebd0`

## callees

- `0x66af0`
- `0x66b00`
- `0x6dbd0`

## string_xrefs

- `0x6dbd1`: `PrincipalObjectAccess`
- `0x6dc7b`: `accessrightsmask`
- `0x6dc9b`: `inheritedaccessrightsmask`
- `0x6dc67`: `D:\a\1\s\src\ManagedPlatform\Server\PrincipalObjectAccessHelper.cs`
- `0x6dbf4`: `SELECT AccessRightsMask, InheritedAccessRightsMask FROM PrincipalObjectAccess WHERE PrincipalId = @PrincipalId AND ObjectId = @ObjectId AND ObjectTypeCode = @ObjectTypeCode`
- `0x6dc81`: `AccessRightsMask`
- `0x6dca1`: `InheritedAccessRightsMask`

## pseudocode

```c

```

## disassembly

```asm
0x6dbd0  ldarg.0
0x6dbd1  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6dbd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6dbdb  ldarg.1
0x6dbdc  ldstr    aExecutionconte_3// "ExecutionContext"
0x6dbe1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6dbe6  ldarg.1
0x6dbe7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x6dbec  stloc.0
0x6dbed  ldloc.0
0x6dbee  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x6dbf3  ldloc.0
0x6dbf4  ldstr    aSelectAccessri// "SELECT AccessRightsMask, InheritedAcces"...
0x6dbf9  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x6dbfe  stloc.1
0x6dbff  ldloc.1
0x6dc00  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6dc05  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x6dc0a  dup
0x6dc0b  ldstr    aPrincipalid_1// "@PrincipalId"
0x6dc10  ldarg.0
0x6dc11  ldstr    aPrincipalid// "principalid"
0x6dc16  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6dc1b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6dc20  pop
0x6dc21  dup
0x6dc22  ldstr    aObjectid_3// "@ObjectId"
0x6dc27  ldarg.0
0x6dc28  ldstr    aObjectid// "objectid"
0x6dc2d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6dc32  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6dc37  pop
0x6dc38  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x6dc3d  ldarg.0
0x6dc3e  ldstr    aObjecttypecode_81// "objecttypecode"
0x6dc43  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6dc48  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6dc4d  pop
0x6dc4e  ldloc.1
0x6dc4f  ldarg.1
0x6dc50  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x6dc55  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x6dc5a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x6dc5f  ldloc.1
0x6dc60  ldc.i4.s 0x62
0x6dc62  ldstr    aRetrieve// "Retrieve"
0x6dc67  ldstr    aDA1SSrcManaged_16// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x6dc6c  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x6dc71  stloc.2
0x6dc72  ldloc.2
0x6dc73  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x6dc78  brfalse.s loc_6DCBA
0x6dc7a  ldarg.0
0x6dc7b  ldstr    aAccessrightsma// "accessrightsmask"
0x6dc80  ldloc.2
0x6dc81  ldstr    aAccessrightsma_1// "AccessRightsMask"
0x6dc86  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6dc8b  unbox.any [mscorlib]System.Int32
0x6dc90  box      [mscorlib]System.Int32
0x6dc95  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x6dc9a  ldarg.0
0x6dc9b  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x6dca0  ldloc.2
0x6dca1  ldstr    aInheritedacces_1// "InheritedAccessRightsMask"
0x6dca6  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x6dcab  unbox.any [mscorlib]System.Int32
0x6dcb0  box      [mscorlib]System.Int32
0x6dcb5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x6dcba  leave.s  loc_6DCD7
0x6dcbc  ldloc.2
0x6dcbd  brfalse.s loc_6DCC5
0x6dcbf  ldloc.2
0x6dcc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6dcc5  endfinally
0x6dcc6  ldloc.1
0x6dcc7  brfalse.s loc_6DCCF
0x6dcc9  ldloc.1
0x6dcca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6dccf  endfinally
0x6dcd0  ldloc.0
0x6dcd1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x6dcd6  endfinally
0x6dcd7  ret
```
