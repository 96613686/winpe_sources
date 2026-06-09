# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::UpdateCalculatedField

- ea: `0x260`
- end: `0x2cc`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::UpdateCalculatedField`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x260`
- `0x340`
- `0x410`

## pseudocode

```c

```

## disassembly

```asm
0x260  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x265  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x26a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CalculatedFields()
0x26f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x274  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x279  brtrue.s loc_28C
0x27b  ldc.i4   0x80060422
0x280  ldc.i4.0
0x281  newarr   [mscorlib]System.Object
0x286  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x28b  throw
0x28c  nop
0x28d  ldarg.0
0x28e  ldarg.1
0x28f  ldarg.2
0x290  ldarg.3
0x291  ldstr    aCalculated// "Calculated"
0x296  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.BusinessRuleAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2a0  call     instance void Microsoft.Crm.Application.WebServices.BusinessRulesWebService::UpdateAttributeRuleDefinition(string ruleAsJson, string entityId, string attributeId, string sourceType, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter ruleAdapter)
0x2a5  leave.s  loc_2CB
0x2a7  stloc.0
0x2a8  ldarg.0
0x2a9  ldloc.0
0x2aa  ldarg.3
0x2ab  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2b0  call     instance void Microsoft.Crm.Application.WebServices.BusinessRulesWebService::HandleUpdateAttributeException(class [System.Web.Services]System.Web.Services.Protocols.SoapException ex, valuetype [mscorlib]System.Guid attributeId)
0x2b5  leave.s  loc_2CB
0x2b7  stloc.1
0x2b8  ldarg.0
0x2b9  ldloc.1
0x2ba  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::ReturnJsonException(class [mscorlib]System.Exception)
0x2bf  ldloc.1
0x2c0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x2c5  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x2ca  throw
0x2cb  ret
```
