# Microsoft.Crm.Service.Web.Tools.ContractTemplatePage::InitializeEntity

- ea: `0x6bf0`
- end: `0x6c05`
- name: `Microsoft.Crm.Service.Web.Tools.ContractTemplatePage::InitializeEntity`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6bf0`: `contracttemplate`

## pseudocode

```c

```

## disassembly

```asm
0x6bf0  ldstr    aContracttempla_0// "contracttemplate"
0x6bf5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6bfa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6bff  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x6c04  ret
```
