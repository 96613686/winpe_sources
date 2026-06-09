# Microsoft.Crm.Tools.Admin.DBImportHelper::MapUsersWithoutAddToConfigDB

- ea: `0x13b50`
- end: `0x13b76`
- name: `Microsoft.Crm.Tools.Admin.DBImportHelper::MapUsersWithoutAddToConfigDB`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14630`

## callees

- `0x22e0`
- `0x13a40`

## string_xrefs

- `0x13b50`: `Organization.Import.UpdateUsers`

## pseudocode

```c

```

## disassembly

```asm
0x13b50  ldstr    aOrganizationIm_0// "Organization.Import.UpdateUsers"
0x13b55  ldc.i4.0
0x13b56  newarr   [mscorlib]System.Object
0x13b5b  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x13b60  ldc.i4.0
0x13b61  newarr   [mscorlib]System.Object
0x13b66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x13b6b  ldarg.0
0x13b6c  ldarg.1
0x13b6d  ldarg.2
0x13b6e  ldc.i4.1
0x13b6f  ldarg.3
0x13b70  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::MapUsers(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> users, string reportingGroupName, bool usersAlreadyInConfigDB, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x13b75  ret
```
