# Microsoft.Crm.Application.WebServices.SystemCustomization.SqlEncryption::SetEncryptionKey

- ea: `0xac60`
- end: `0xac94`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SqlEncryption::SetEncryptionKey`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb600`

## callees

- `0xac60`

## pseudocode

```c

```

## disassembly

```asm
0xac60  ldarg.1
0xac61  brtrue.s loc_AC6A
0xac63  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_RestoreSqlEncryptionKey()
0xac68  br.s     loc_AC6F
0xac6a  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ChangeSqlEncryptionKey()
0xac6f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xac74  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xac79  brtrue.s loc_AC8C
0xac7b  ldc.i4   0x80040277
0xac80  ldc.i4.0
0xac81  newarr   [mscorlib]System.Object
0xac86  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xac8b  throw
0xac8c  ldarg.0
0xac8d  ldarg.1
0xac8e  call     void [Microsoft.Crm.MetadataService]Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionService::SetEncryptionKey(string, bool)
0xac93  ret
```
