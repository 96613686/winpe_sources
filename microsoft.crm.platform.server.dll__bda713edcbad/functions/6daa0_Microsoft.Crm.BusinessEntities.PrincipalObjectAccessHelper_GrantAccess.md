# Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantAccess

- ea: `0x6daa0`
- end: `0x6dba4`
- name: `Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::GrantAccess`
- size: `260`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x57760`
- `0x6dff0`
- `0x6e140`
- `0x6e390`
- `0x74140`
- `0x743a0`

## callees

- `0x66ae0`
- `0x66b00`
- `0x6daa0`
- `0x6dbb0`

## string_xrefs

- `0x6daa1`: `PrincipalObjectAccess`
- `0x6db3f`: `accessrightsmask`
- `0x6db55`: `inheritedaccessrightsmask`
- `0x6db79`: `GrantAccess`
- `0x6dac3`: `IF EXISTS( SELECT PrincipalId FROM PrincipalObjectAccess WHERE PrincipalId = @PrincipalId AND ObjectId = @ObjectId AND ObjectTypeCode = @ObjectTypeCode)\n  UPDATE PrincipalObjectAccess SET AccessRightsMask = AccessRightsMask | @AccessRightsMask, InheritedAccessRightsMask = COALESCE(InheritedAccessRightsMask, 0) | @InheritedAccessRightsMask, ChangedOn = getutcdate() WHERE PrincipalId = @PrincipalId AND ObjectId = @ObjectId AND @ObjectTypeCode = ObjectTypeCode\n   ELSE INSERT INTO PrincipalObjec`
- `0x6db39`: `@AccessRightsMask`
- `0x6db4f`: `@InheritedAccessRightsMask`
- `0x6db7e`: `D:\a\1\s\src\ManagedPlatform\Server\PrincipalObjectAccessHelper.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6daa0  ldarg.0
0x6daa1  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6daa6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6daab  ldarg.1
0x6daac  ldstr    aExecutionconte_3// "ExecutionContext"
0x6dab1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6dab6  ldarg.1
0x6dab7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x6dabc  stloc.0
0x6dabd  ldloc.0
0x6dabe  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x6dac3  ldstr    aIfExistsSelect_3// "IF EXISTS( SELECT PrincipalId FROM Prin"...
0x6dac8  stloc.1
0x6dac9  ldloc.0
0x6daca  ldloc.1
0x6dacb  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x6dad0  stloc.2
0x6dad1  ldloc.2
0x6dad2  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6dad7  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x6dadc  dup
0x6dadd  ldstr    aPrincipalid_1// "@PrincipalId"
0x6dae2  ldarg.0
0x6dae3  ldstr    aPrincipalid// "principalid"
0x6dae8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6daed  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6daf2  pop
0x6daf3  dup
0x6daf4  ldstr    aObjectid_3// "@ObjectId"
0x6daf9  ldarg.0
0x6dafa  ldstr    aObjectid// "objectid"
0x6daff  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6db04  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6db09  pop
0x6db0a  dup
0x6db0b  ldstr    aPrincipaltypec_0// "@PrincipalTypeCode"
0x6db10  ldarg.0
0x6db11  ldstr    aPrincipaltypec// "principaltypecode"
0x6db16  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6db1b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6db20  pop
0x6db21  dup
0x6db22  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x6db27  ldarg.0
0x6db28  ldstr    aObjecttypecode_81// "objecttypecode"
0x6db2d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6db32  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6db37  pop
0x6db38  dup
0x6db39  ldstr    aAccessrightsma_0// "@AccessRightsMask"
0x6db3e  ldarg.0
0x6db3f  ldstr    aAccessrightsma// "accessrightsmask"
0x6db44  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6db49  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6db4e  pop
0x6db4f  ldstr    aInheritedacces_0// "@InheritedAccessRightsMask"
0x6db54  ldarg.0
0x6db55  ldstr    aInheritedacces// "inheritedaccessrightsmask"
0x6db5a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6db5f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6db64  pop
0x6db65  ldloc.2
0x6db66  ldarg.1
0x6db67  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x6db6c  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x6db71  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x6db76  ldloc.2
0x6db77  ldc.i4.s 0x38
0x6db79  ldstr    aGrantaccess// "GrantAccess"
0x6db7e  ldstr    aDA1SSrcManaged_16// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x6db83  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x6db88  brfalse.s loc_6DB90
0x6db8a  ldarg.1
0x6db8b  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RegisterHandlerAndTrackPOA(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6db90  leave.s  loc_6DBA3
0x6db92  ldloc.2
0x6db93  brfalse.s loc_6DB9B
0x6db95  ldloc.2
0x6db96  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6db9b  endfinally
0x6db9c  ldloc.0
0x6db9d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x6dba2  endfinally
0x6dba3  ret
```
