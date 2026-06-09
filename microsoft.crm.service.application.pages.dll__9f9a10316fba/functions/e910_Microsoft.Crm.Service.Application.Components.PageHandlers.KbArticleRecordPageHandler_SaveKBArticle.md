# Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::SaveKBArticle

- ea: `0xe910`
- end: `0xe93f`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::SaveKBArticle`
- size: `47`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xe7a0`
- `0xe800`
- `0xe860`

## callees

- `0xe910`

## pseudocode

```c

```

## disassembly

```asm
0xe910  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteArticle()
0xe915  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe91a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe91f  brfalse.s loc_E93E
0xe921  ldarg.1
0xe922  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0xe927  brfalse.s loc_E930
0xe929  ldarg.1
0xe92a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Create()
0xe92f  ret
0xe930  ldarg.1
0xe931  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_HasData()
0xe936  brfalse.s loc_E93E
0xe938  ldarg.1
0xe939  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0xe93e  ret
```
