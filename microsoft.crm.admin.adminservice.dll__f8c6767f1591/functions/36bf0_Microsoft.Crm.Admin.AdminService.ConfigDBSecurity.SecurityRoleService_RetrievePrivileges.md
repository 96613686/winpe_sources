# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RetrievePrivileges

- ea: `0x36bf0`
- end: `0x36caa`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRoleService::RetrievePrivileges`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x36500`
- `0x36bf0`
- `0x37180`

## string_xrefs

- `0x36c4b`: `D:\a\1\s\src\CrmLive\Admin\Security\SecurityRoleService.cs`
- `0x36c12`: `exec p_GetPrivilegesInRole @roleName`
- `0x36c46`: `RetrievePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x36bf0  ldarg.1
0x36bf1  call     void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityOnPremiseAndSplaExceptionHelper::ThrowIfSecurityRoleIsNotValid(valuetype Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole securityRole)
0x36bf6  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x36bfb  stloc.0
0x36bfc  ldloc.0
0x36bfd  ldc.i4.0
0x36bfe  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::NewConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x36c03  stloc.1
0x36c04  ldloc.1
0x36c05  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x36c0a  ldloc.1
0x36c0b  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x36c10  stloc.2
0x36c11  ldloc.2
0x36c12  ldstr    aExecPGetprivil// "exec p_GetPrivilegesInRole @roleName"
0x36c17  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x36c1c  ldloc.2
0x36c1d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x36c22  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x36c27  ldstr    aRolename// "@roleName"
0x36c2c  ldarga.s 1
0x36c2e  constrained. Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SecurityRole
0x36c34  callvirt instance string [mscorlib]System.Object::ToString()
0x36c39  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36c3e  pop
0x36c3f  ldloc.2
0x36c40  ldc.i4.1
0x36c41  ldc.i4   0x10E
0x36c46  ldstr    aRetrieveprivil// "RetrievePrivileges"
0x36c4b  ldstr    aDA1SSrcCrmlive_63// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x36c50  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, bool, int32, string, string)
0x36c55  stloc.3
0x36c56  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.PrivilegeData>::.ctor()
0x36c5b  stloc.s  4
0x36c5d  br.s     loc_36C6C
0x36c5f  ldloc.s  4
0x36c61  ldloc.3
0x36c62  newobj   instance void Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.PrivilegeData::.ctor(class [System.Data]System.Data.IDataRecord record)
0x36c67  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.PrivilegeData>::Add(var<u1>)
0x36c6c  ldloc.3
0x36c6d  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x36c72  brtrue.s loc_36C5F
0x36c74  ldloc.s  4
0x36c76  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.PrivilegeData>::ToArray()
0x36c7b  stloc.s  5
0x36c7d  leave.s  loc_36CA7
0x36c7f  ldloc.3
0x36c80  brfalse.s loc_36C88
0x36c82  ldloc.3
0x36c83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36c88  endfinally
0x36c89  ldloc.2
0x36c8a  brfalse.s loc_36C92
0x36c8c  ldloc.2
0x36c8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36c92  endfinally
0x36c93  ldloc.1
0x36c94  brfalse.s loc_36C9C
0x36c96  ldloc.1
0x36c97  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36c9c  endfinally
0x36c9d  ldloc.0
0x36c9e  brfalse.s loc_36CA6
0x36ca0  ldloc.0
0x36ca1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36ca6  endfinally
0x36ca7  ldloc.s  5
0x36ca9  ret
```
