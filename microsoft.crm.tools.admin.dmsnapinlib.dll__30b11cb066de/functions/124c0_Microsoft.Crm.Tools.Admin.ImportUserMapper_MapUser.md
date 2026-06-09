# Microsoft.Crm.Tools.Admin.ImportUserMapper::MapUser

- ea: `0x124c0`
- end: `0x12530`
- name: `Microsoft.Crm.Tools.Admin.ImportUserMapper::MapUser`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x124c0`
- `0x12530`
- `0x12550`

## string_xrefs

- `0x124c0`: `Attempting to map user "{0}" with account {1}`
- `0x124f8`: `Error occurred while attempting to map user "{0}" with account {1} during user mapping: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x124c0  ldstr    aAttemptingToMa// "Attempting to map user \"{0}\" with acc"...
0x124c5  ldc.i4.2
0x124c6  newarr   [mscorlib]System.Object
0x124cb  dup
0x124cc  ldc.i4.0
0x124cd  ldarg.1
0x124ce  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBFullName()
0x124d3  stelem.ref
0x124d4  dup
0x124d5  ldc.i4.1
0x124d6  ldarg.1
0x124d7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBDomainName()
0x124dc  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x124e1  stelem.ref
0x124e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x124e7  ldarg.0
0x124e8  ldarg.1
0x124e9  callvirt instance void Microsoft.Crm.Tools.Admin.ImportUserMapper::MapUserAccountInfo(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User user)
0x124ee  ldarg.0
0x124ef  ldarg.1
0x124f0  call     instance void Microsoft.Crm.Tools.Admin.ImportUserMapper::ValidateMapping(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User user)
0x124f5  leave.s  loc_1252F
0x124f7  stloc.0
0x124f8  ldstr    aErrorOccurredW// "Error occurred while attempting to map "...
0x124fd  ldc.i4.3
0x124fe  newarr   [mscorlib]System.Object
0x12503  dup
0x12504  ldc.i4.0
0x12505  ldarg.1
0x12506  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBFullName()
0x1250b  stelem.ref
0x1250c  dup
0x1250d  ldc.i4.1
0x1250e  ldarg.1
0x1250f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::get_DBDomainName()
0x12514  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x12519  stelem.ref
0x1251a  dup
0x1251b  ldc.i4.2
0x1251c  ldloc.0
0x1251d  stelem.ref
0x1251e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x12523  ldloc.0
0x12524  isinst   [System.Data]System.Data.SqlClient.SqlException
0x12529  brfalse.s loc_1252D
0x1252b  rethrow
0x1252d  leave.s  loc_1252F
0x1252f  ret
```
