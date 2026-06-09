# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::RetrieveRuleJson

- ea: `0x580`
- end: `0x5c1`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::RetrieveRuleJson`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x580`

## pseudocode

```c

```

## disassembly

```asm
0x580  ldarga.s 1
0x582  constrained. [mscorlib]System.Guid
0x588  callvirt instance string [mscorlib]System.Object::ToString()
0x58d  ldstr    aRuleid// "ruleId"
0x592  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x597  ldarg.0
0x598  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter Microsoft.Crm.Application.WebServices.BusinessRulesWebService::_businessRuleAdapter
0x59d  ldarg.1
0x59e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.IBusinessRuleEntityProxy [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter::RetrieveRule(valuetype [mscorlib]System.Guid)
0x5a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.IProcessEntityProxy::get_Json()
0x5a8  stloc.0
0x5a9  leave.s  loc_5BF
0x5ab  stloc.1
0x5ac  ldarg.0
0x5ad  ldloc.1
0x5ae  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::ReturnJsonException(class [mscorlib]System.Exception)
0x5b3  ldloc.1
0x5b4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x5b9  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5be  throw
0x5bf  ldloc.0
0x5c0  ret
```
