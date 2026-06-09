# Microsoft.Crm.Service.Web.Tools.ContractTemplatePrintPage::InitializeEntity

- ea: `0x6db0`
- end: `0x6dc5`
- name: `Microsoft.Crm.Service.Web.Tools.ContractTemplatePrintPage::InitializeEntity`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6db0`: `contracttemplate`

## pseudocode

```c

```

## disassembly

```asm
0x6db0  ldstr    aContracttempla_0// "contracttemplate"
0x6db5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6dba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6dbf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x6dc4  ret
```
