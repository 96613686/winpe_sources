# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::Update

- ea: `0x230`
- end: `0x260`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::Update`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x230`

## string_xrefs

- `0x231`: `ruleAsJson`

## pseudocode

```c

```

## disassembly

```asm
0x230  ldarg.1
0x231  ldstr    aRuleasjson// "ruleAsJson"
0x236  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x23b  ldarg.0
0x23c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter Microsoft.Crm.Application.WebServices.BusinessRulesWebService::_businessRuleAdapter
0x241  ldarg.1
0x242  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter::UpdateRule(string)
0x247  stloc.0
0x248  leave.s  loc_25E
0x24a  stloc.1
0x24b  ldarg.0
0x24c  ldloc.1
0x24d  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::ReturnJsonException(class [mscorlib]System.Exception)
0x252  ldloc.1
0x253  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x258  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x25d  throw
0x25e  ldloc.0
0x25f  ret
```
