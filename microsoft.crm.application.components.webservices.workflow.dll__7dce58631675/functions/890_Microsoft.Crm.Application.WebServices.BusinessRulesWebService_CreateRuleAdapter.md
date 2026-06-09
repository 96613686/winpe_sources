# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::CreateRuleAdapter

- ea: `0x890`
- end: `0x8c4`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::CreateRuleAdapter`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x630`
- `0x690`

## callees

- `0x890`

## pseudocode

```c

```

## disassembly

```asm
0x890  ldnull
0x891  stloc.0
0x892  ldarg.1
0x893  switch   loc_8B7, loc_8B7, loc_8AA, loc_8B7
0x8a8  br.s     loc_8B7
0x8aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8af  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.RollupFields.RollupFieldAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8b4  stloc.0
0x8b5  br.s     loc_8C2
0x8b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8bc  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c1  stloc.0
0x8c2  ldloc.0
0x8c3  ret
```
