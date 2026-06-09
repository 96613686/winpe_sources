# Microsoft.Crm.Tools.Admin.DBImportHelper::AddUsersToConfigDB

- ea: `0x13950`
- end: `0x13a39`
- name: `Microsoft.Crm.Tools.Admin.DBImportHelper::AddUsersToConfigDB`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14630`

## callees

- `0x22e0`
- `0x13950`

## string_xrefs

- `0x1397a`: `System Administrator "{0}" with account {1} was added to the configDB successfully`

## pseudocode

```c

```

## disassembly

```asm
0x13950  ldc.i4.0
0x13951  stloc.0
0x13952  ldarg.0
0x13953  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::GetEnumerator()
0x13958  stloc.1
0x13959  br       loc_139DE
0x1395e  ldloc.1
0x1395f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::get_Current()
0x13964  stloc.2
0x13965  ldloc.2
0x13966  ldarg.1
0x13967  ldarg.2
0x13968  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UserMapper::AddUserToConfigDB(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.UserValidationParameters, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1396d  stloc.3
0x1396e  ldloc.2
0x1396f  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBIsSystemAdminRole()
0x13974  ldloc.3
0x13975  and
0x13976  brfalse.s loc_139A1
0x13978  ldc.i4.1
0x13979  stloc.0
0x1397a  ldstr    aSystemAdminist// "System Administrator \"{0}\" with accou"...
0x1397f  ldc.i4.2
0x13980  newarr   [mscorlib]System.Object
0x13985  dup
0x13986  ldc.i4.0
0x13987  ldloc.2
0x13988  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBFullName()
0x1398d  stelem.ref
0x1398e  dup
0x1398f  ldc.i4.1
0x13990  ldloc.2
0x13991  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_ADDomainAccount()
0x13996  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x1399b  stelem.ref
0x1399c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x139a1  leave.s  loc_139DE
0x139a3  stloc.s  4
0x139a5  ldstr    aAnErrorWasEnco// "An error was encountered while working "...
0x139aa  ldc.i4.3
0x139ab  newarr   [mscorlib]System.Object
0x139b0  dup
0x139b1  ldc.i4.0
0x139b2  ldloc.2
0x139b3  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBFullName()
0x139b8  stelem.ref
0x139b9  dup
0x139ba  ldc.i4.1
0x139bb  ldloc.2
0x139bc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_ADDomainAccount()
0x139c1  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x139c6  stelem.ref
0x139c7  dup
0x139c8  ldc.i4.2
0x139c9  ldloc.s  4
0x139cb  stelem.ref
0x139cc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x139d1  ldloc.s  4
0x139d3  isinst   [System.Data]System.Data.SqlClient.SqlException
0x139d8  brfalse.s loc_139DC
0x139da  rethrow
0x139dc  leave.s  loc_139DE
0x139de  ldloc.1
0x139df  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x139e4  brtrue   loc_1395E
0x139e9  leave.s  loc_139F5
0x139eb  ldloc.1
0x139ec  brfalse.s loc_139F4
0x139ee  ldloc.1
0x139ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x139f4  endfinally
0x139f5  ldloc.0
0x139f6  brtrue.s loc_13A38
0x139f8  ldstr    aNoSystemAdmini// "No system administrator was successfull"...
0x139fd  ldc.i4.0
0x139fe  newarr   [mscorlib]System.Object
0x13a03  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x13a08  ldstr    aImportcurrentu// "ImportCurrentUserMapingValidator.MapToV"...
0x13a0d  ldc.i4.0
0x13a0e  newarr   [mscorlib]System.Object
0x13a13  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x13a18  call     string [mscorlib]System.Environment::get_NewLine()
0x13a1d  ldstr    aImportorganiza// "ImportOrganization.ViewLogFile"
0x13a22  ldc.i4.0
0x13a23  newarr   [mscorlib]System.Object
0x13a28  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x13a2d  call     string [mscorlib]System.String::Concat(string, string, string)
0x13a32  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x13a37  throw
0x13a38  ret
```
