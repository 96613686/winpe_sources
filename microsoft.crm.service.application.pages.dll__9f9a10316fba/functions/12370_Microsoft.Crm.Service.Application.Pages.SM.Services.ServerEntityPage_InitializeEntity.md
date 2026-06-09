# Microsoft.Crm.Service.Application.Pages.SM.Services.ServerEntityPage::InitializeEntity

- ea: `0x12370`
- end: `0x12396`
- name: `Microsoft.Crm.Service.Application.Pages.SM.Services.ServerEntityPage::InitializeEntity`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12370`: `service`

## pseudocode

```c

```

## disassembly

```asm
0x12370  ldstr    aService_0// "service"
0x12375  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1237a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1237f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x12384  dup
0x12385  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_RequiredColumns()
0x1238a  ldstr    aIsschedulable// "isschedulable"
0x1238f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12394  pop
0x12395  ret
```
