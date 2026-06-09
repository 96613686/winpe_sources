# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::.ctor

- ea: `0x1e0`
- end: `0x1f7`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::.ctor`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1e0  ldarg.0
0x1e1  call     instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::.ctor()
0x1e6  ldarg.0
0x1e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ec  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f1  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter Microsoft.Crm.Application.WebServices.BusinessRulesWebService::_businessRuleAdapter
0x1f6  ret
```
