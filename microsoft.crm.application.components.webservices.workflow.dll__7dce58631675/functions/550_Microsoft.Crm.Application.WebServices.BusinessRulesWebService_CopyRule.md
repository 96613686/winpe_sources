# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::CopyRule

- ea: `0x550`
- end: `0x580`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::CopyRule`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x550`

## string_xrefs

- `0x551`: `ruleAsJson`

## pseudocode

```c

```

## disassembly

```asm
0x550  ldarg.1
0x551  ldstr    aRuleasjson// "ruleAsJson"
0x556  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x55b  ldarg.0
0x55c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter Microsoft.Crm.Application.WebServices.BusinessRulesWebService::_businessRuleAdapter
0x561  ldarg.1
0x562  callvirt instance string[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter::CopyRule(string)
0x567  stloc.0
0x568  leave.s  loc_57E
0x56a  stloc.1
0x56b  ldarg.0
0x56c  ldloc.1
0x56d  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::ReturnJsonException(class [mscorlib]System.Exception)
0x572  ldloc.1
0x573  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x578  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x57d  throw
0x57e  ldloc.0
0x57f  ret
```
