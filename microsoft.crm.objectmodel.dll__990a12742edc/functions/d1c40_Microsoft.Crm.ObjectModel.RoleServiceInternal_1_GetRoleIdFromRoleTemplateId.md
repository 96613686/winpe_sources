# Microsoft.Crm.ObjectModel.RoleServiceInternal`1::GetRoleIdFromRoleTemplateId

- ea: `0xd1c40`
- end: `0xd1cec`
- name: `Microsoft.Crm.ObjectModel.RoleServiceInternal`1::GetRoleIdFromRoleTemplateId`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xd1c40`

## string_xrefs

- `0xd1c6e`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\RoleService.cs`
- `0xd1cce`: `D:\a\1\s\src\Core\ObjectModel\Services\BusinessManagement\RoleService.cs`
- `0xd1c41`: `roleTemplateId`
- `0xd1c69`: `GetRoleIdFromRoleTemplateId`
- `0xd1cc9`: `GetRoleIdFromRoleTemplateId`
- `0xd1c7f`: `select RoleId from Role where BusinessUnitId = @BusinessUnitId and RoleTemplateId = @RoleTemplateId`
- `0xd1cb2`: `@RoleTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0xd1c40  ldarg.1
0xd1c41  ldstr    aRoletemplateid_0// "roleTemplateId"
0xd1c46  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xd1c4b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd1c50  stloc.0
0xd1c51  ldarg.2
0xd1c52  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0xd1c57  stloc.1
0xd1c58  ldloc.1
0xd1c59  ldstr    aSelectBusiness// "select BusinessUnitId from BusinessUnit"...
0xd1c5e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd1c63  ldloc.1
0xd1c64  ldc.i4   0x194
0xd1c69  ldstr    aGetroleidfromr// "GetRoleIdFromRoleTemplateId"
0xd1c6e  ldstr    aDA1SSrcCoreObj_22// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xd1c73  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xd1c78  unbox.any [mscorlib]System.Guid
0xd1c7d  stloc.2
0xd1c7e  ldloc.1
0xd1c7f  ldstr    aSelectRoleidFr_0// "select RoleId from Role where BusinessU"...
0xd1c84  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd1c89  ldloc.1
0xd1c8a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd1c8f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd1c94  pop
0xd1c95  ldloc.1
0xd1c96  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd1c9b  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd1ca0  dup
0xd1ca1  ldstr    aBusinessunitid_0// "@BusinessUnitId"
0xd1ca6  ldloc.2
0xd1ca7  box      [mscorlib]System.Guid
0xd1cac  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd1cb1  pop
0xd1cb2  ldstr    aRoletemplateid_1// "@RoleTemplateId"
0xd1cb7  ldarg.1
0xd1cb8  box      [mscorlib]System.Guid
0xd1cbd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd1cc2  pop
0xd1cc3  ldloc.1
0xd1cc4  ldc.i4   0x19D
0xd1cc9  ldstr    aGetroleidfromr// "GetRoleIdFromRoleTemplateId"
0xd1cce  ldstr    aDA1SSrcCoreObj_22// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0xd1cd3  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xd1cd8  unbox.any [mscorlib]System.Guid
0xd1cdd  stloc.0
0xd1cde  leave.s  loc_D1CEA
0xd1ce0  ldloc.1
0xd1ce1  brfalse.s loc_D1CE9
0xd1ce3  ldloc.1
0xd1ce4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1ce9  endfinally
0xd1cea  ldloc.0
0xd1ceb  ret
```
