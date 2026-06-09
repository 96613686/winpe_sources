# Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RevokeAccess

- ea: `0x6dce0`
- end: `0x6de1e`
- name: `Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RevokeAccess`
- size: `318`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x57860`
- `0x57a40`
- `0x73ee0`
- `0x743a0`
- `0x745d0`

## callees

- `0x66ae0`
- `0x66b00`
- `0x6dbb0`
- `0x6dce0`

## string_xrefs

- `0x6dce1`: `PrincipalObjectAccess`
- `0x6ddf2`: `RevokeAccess`
- `0x6ddf7`: `D:\a\1\s\src\ManagedPlatform\Server\PrincipalObjectAccessHelper.cs`
- `0x6dd07`: `UPDATE PrincipalObjectAccess SET `
- `0x6dd1d`: `AccessRightsMask = 0`
- `0x6dd44`: `InheritedAccessRightsMask = 0`
- `0x6dd61`: ` AND InheritedAccessRightsMask <> 0`

## pseudocode

```c

```

## disassembly

```asm
0x6dce0  ldarg.0
0x6dce1  ldstr    aPrincipalobjec// "PrincipalObjectAccess"
0x6dce6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6dceb  ldarg.2
0x6dcec  ldstr    aExecutionconte_3// "ExecutionContext"
0x6dcf1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6dcf6  ldarg.1
0x6dcf7  brtrue.s loc_6DCFA
0x6dcf9  ret
0x6dcfa  ldarg.2
0x6dcfb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x6dd00  stloc.0
0x6dd01  ldloc.0
0x6dd02  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x6dd07  ldstr    aUpdatePrincipa_0// "UPDATE PrincipalObjectAccess SET "
0x6dd0c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x6dd11  stloc.1
0x6dd12  ldarg.1
0x6dd13  ldc.i4.1
0x6dd14  and
0x6dd15  ldc.i4.1
0x6dd16  ceq
0x6dd18  stloc.2
0x6dd19  ldloc.2
0x6dd1a  brfalse.s loc_6DD28
0x6dd1c  ldloc.1
0x6dd1d  ldstr    aAccessrightsma_2// "AccessRightsMask = 0"
0x6dd22  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6dd27  pop
0x6dd28  ldarg.1
0x6dd29  ldc.i4.3
0x6dd2a  and
0x6dd2b  ldc.i4.3
0x6dd2c  bne.un.s loc_6DD3A
0x6dd2e  ldloc.1
0x6dd2f  ldstr    asc_CC16C// ", "
0x6dd34  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6dd39  pop
0x6dd3a  ldarg.1
0x6dd3b  ldc.i4.2
0x6dd3c  and
0x6dd3d  ldc.i4.2
0x6dd3e  ceq
0x6dd40  dup
0x6dd41  brfalse.s loc_6DD4F
0x6dd43  ldloc.1
0x6dd44  ldstr    aInheritedacces_2// "InheritedAccessRightsMask = 0"
0x6dd49  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6dd4e  pop
0x6dd4f  ldloc.1
0x6dd50  ldstr    aWhereObjectidO// " WHERE ObjectId = @ObjectId"
0x6dd55  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6dd5a  pop
0x6dd5b  brfalse.s loc_6DD6C
0x6dd5d  ldloc.2
0x6dd5e  brtrue.s loc_6DD6C
0x6dd60  ldloc.1
0x6dd61  ldstr    aAndInheritedac// " AND InheritedAccessRightsMask <> 0"
0x6dd66  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6dd6b  pop
0x6dd6c  ldarg.0
0x6dd6d  ldstr    aPrincipalid// "principalid"
0x6dd72  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x6dd77  ldc.i4.0
0x6dd78  ceq
0x6dd7a  stloc.3
0x6dd7b  ldloc.3
0x6dd7c  brfalse.s loc_6DD8A
0x6dd7e  ldloc.1
0x6dd7f  ldstr    aAndPrincipalid_0// " AND PrincipalId = @PrincipalId"
0x6dd84  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x6dd89  pop
0x6dd8a  ldloc.0
0x6dd8b  ldloc.1
0x6dd8c  callvirt instance string [mscorlib]System.Object::ToString()
0x6dd91  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x6dd96  stloc.s  4
0x6dd98  ldloc.s  4
0x6dd9a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6dd9f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x6dda4  stloc.s  5
0x6dda6  ldloc.s  5
0x6dda8  ldstr    aObjectid_3// "@ObjectId"
0x6ddad  ldarg.0
0x6ddae  ldstr    aObjectid// "objectid"
0x6ddb3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6ddb8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6ddbd  pop
0x6ddbe  ldloc.3
0x6ddbf  brfalse.s loc_6DDD9
0x6ddc1  ldloc.s  5
0x6ddc3  ldstr    aPrincipalid_1// "@PrincipalId"
0x6ddc8  ldarg.0
0x6ddc9  ldstr    aPrincipalid// "principalid"
0x6ddce  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6ddd3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6ddd8  pop
0x6ddd9  ldloc.s  4
0x6dddb  ldarg.2
0x6dddc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x6dde1  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x6dde6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x6ddeb  ldloc.s  4
0x6dded  ldc.i4   0xAD
0x6ddf2  ldstr    aRevokeaccess// "RevokeAccess"
0x6ddf7  ldstr    aDA1SSrcManaged_16// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x6ddfc  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x6de01  pop
0x6de02  ldarg.2
0x6de03  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RegisterHandlerAndTrackPOA(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6de08  leave.s  loc_6DE1D
0x6de0a  ldloc.s  4
0x6de0c  brfalse.s loc_6DE15
0x6de0e  ldloc.s  4
0x6de10  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6de15  endfinally
0x6de16  ldloc.0
0x6de17  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x6de1c  endfinally
0x6de1d  ret
```
