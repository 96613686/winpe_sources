# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::Create

- ea: `0x200`
- end: `0x230`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::Create`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x200`

## string_xrefs

- `0x201`: `ruleAsJson`

## pseudocode

```c

```

## disassembly

```asm
0x200  ldarg.1
0x201  ldstr    aRuleasjson// "ruleAsJson"
0x206  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x20b  ldarg.0
0x20c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter Microsoft.Crm.Application.WebServices.BusinessRulesWebService::_businessRuleAdapter
0x211  ldarg.1
0x212  callvirt instance string[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter::CreateRule(string)
0x217  stloc.0
0x218  leave.s  loc_22E
0x21a  stloc.1
0x21b  ldarg.0
0x21c  ldloc.1
0x21d  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::ReturnJsonException(class [mscorlib]System.Exception)
0x222  ldloc.1
0x223  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x228  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x22d  throw
0x22e  ldloc.0
0x22f  ret
```
