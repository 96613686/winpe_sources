# Microsoft.Crm.Tools.Admin.ImportUserMapper::ReadUsersFromDatabase

- ea: `0x12490`
- end: `0x124c0`
- name: `Microsoft.Crm.Tools.Admin.ImportUserMapper::ReadUsersFromDatabase`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x123c0`

## callees

- `0x12260`
- `0x12280`
- `0x122d0`
- `0x122e0`
- `0x12300`
- `0x13c90`
- `0x197a0`

## pseudocode

```c

```

## disassembly

```asm
0x12490  ldarg.0
0x12491  ldarg.0
0x12492  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventSource Microsoft.Crm.Tools.Admin.ImportUserMapper::get_ProgressProvider()
0x12497  ldarg.0
0x12498  call     instance int32 Microsoft.Crm.Tools.Admin.ImportUserMapper::get_ProgressLimit()
0x1249d  ldarg.0
0x1249e  ldftn    instance void Microsoft.Crm.Tools.Admin.ImportUserMapper::MapUser(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User user)
0x124a4  newobj   instance void UserAccountMapper::.ctor(object object, native int method)
0x124a9  ldarg.0
0x124aa  call     instance string Microsoft.Crm.Tools.Admin.ImportUserMapper::get_SqlServerName()
0x124af  ldarg.0
0x124b0  call     instance string Microsoft.Crm.Tools.Admin.ImportUserMapper::get_DatabaseName()
0x124b5  call     class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> Microsoft.Crm.Tools.Admin.DBImportHelper::ReadUsers(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource progressHandler, int32 progressLimit, class UserAccountMapper mapUserAccountInfo, string sqlServerName, string databaseName)
0x124ba  call     instance void Microsoft.Crm.Tools.Admin.ImportUserMapper::set_Users(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> value)
0x124bf  ret
```
