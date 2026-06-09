# <>c__DisplayClass1_0::<GrantAccess>b__0

- ea: `0x8f330`
- end: `0x8f468`
- name: `<>c__DisplayClass1_0::<GrantAccess>b__0`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x61160`
- `0x61180`
- `0x61300`
- `0x61320`
- `0x66af0`
- `0x66b00`
- `0x6dbb0`
- `0x8f330`

## string_xrefs

- `0x8f440`: `GrantAccess`
- `0x8f33b`: `exec p_CascadeGrantAccess @principal_id, @principal_type, @root_entity_otc, @root_entity_oid, @access_rights, @inherited_access_rights`
- `0x8f3f4`: `@access_rights`
- `0x8f414`: `@inherited_access_rights`

## pseudocode

```c

```

## disassembly

```asm
0x8f330  ldarg.0
0x8f331  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass1_0::context
0x8f336  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x8f33b  ldstr    aExecPCascadegr// "exec p_CascadeGrantAccess @principal_id"...
0x8f340  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x8f345  stloc.0
0x8f346  ldloc.0
0x8f347  ldarg.0
0x8f348  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass1_0::context
0x8f34d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8f352  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x8f357  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x8f35c  ldloc.0
0x8f35d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x8f362  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x8f367  dup
0x8f368  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x8f36d  dup
0x8f36e  ldstr    aPrincipalId// "@principal_id"
0x8f373  ldc.i4.s 0xE
0x8f375  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x8f37a  ldarg.0
0x8f37b  ldfld    class Microsoft.Crm.BusinessEntities.PrincipalAccess <>c__DisplayClass1_0::grantee
0x8f380  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.PrincipalAccess::get_Principal()
0x8f385  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x8f38a  box      [mscorlib]System.Guid
0x8f38f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x8f394  dup
0x8f395  ldstr    aPrincipalType// "@principal_type"
0x8f39a  ldc.i4.8
0x8f39b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x8f3a0  ldarg.0
0x8f3a1  ldfld    class Microsoft.Crm.BusinessEntities.PrincipalAccess <>c__DisplayClass1_0::grantee
0x8f3a6  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.PrincipalAccess::get_Principal()
0x8f3ab  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x8f3b0  box      [mscorlib]System.Int32
0x8f3b5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x8f3ba  dup
0x8f3bb  ldstr    aRootEntityOtc// "@root_entity_otc"
0x8f3c0  ldc.i4.8
0x8f3c1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x8f3c6  ldarg.0
0x8f3c7  ldfld    int32 <>c__DisplayClass1_0::rootEntityOtc
0x8f3cc  box      [mscorlib]System.Int32
0x8f3d1  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x8f3d6  dup
0x8f3d7  ldstr    aRootEntityOid// "@root_entity_oid"
0x8f3dc  ldc.i4.s 0xE
0x8f3de  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x8f3e3  ldarg.0
0x8f3e4  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass1_0::rootEntityId
0x8f3e9  box      [mscorlib]System.Guid
0x8f3ee  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x8f3f3  dup
0x8f3f4  ldstr    aAccessRights// "@access_rights"
0x8f3f9  ldc.i4.8
0x8f3fa  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x8f3ff  ldarg.0
0x8f400  ldfld    class Microsoft.Crm.BusinessEntities.PrincipalAccess <>c__DisplayClass1_0::grantee
0x8f405  callvirt instance int32 Microsoft.Crm.BusinessEntities.PrincipalAccess::get_AccessMask()
0x8f40a  box      [mscorlib]System.Int32
0x8f40f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x8f414  ldstr    aInheritedAcces// "@inherited_access_rights"
0x8f419  ldc.i4.8
0x8f41a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x8f41f  ldarg.0
0x8f420  ldfld    class Microsoft.Crm.BusinessEntities.PrincipalAccess <>c__DisplayClass1_0::grantee
0x8f425  callvirt instance int32 Microsoft.Crm.BusinessEntities.PrincipalAccess::get_AccessMask()
0x8f42a  ldc.i4   0x8000000
0x8f42f  or
0x8f430  box      [mscorlib]System.Int32
0x8f435  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x8f43a  ldloc.0
0x8f43b  ldc.i4   0x18A
0x8f440  ldstr    aGrantaccess// "GrantAccess"
0x8f445  ldstr    aDA1SSrcManaged_14// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x8f44a  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x8f44f  pop
0x8f450  ldarg.0
0x8f451  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass1_0::context
0x8f456  call     void Microsoft.Crm.BusinessEntities.PrincipalObjectAccessHelper::RegisterHandlerAndTrackPOA(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8f45b  leave.s  loc_8F467
0x8f45d  ldloc.0
0x8f45e  brfalse.s loc_8F466
0x8f460  ldloc.0
0x8f461  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8f466  endfinally
0x8f467  ret
```
