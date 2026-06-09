# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::UpdateRollupField

- ea: `0x2d0`
- end: `0x33c`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::UpdateRollupField`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2d0`
- `0x340`
- `0x410`

## pseudocode

```c

```

## disassembly

```asm
0x2d0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x2d5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x2da  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_Rollups()
0x2df  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2e4  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2e9  brtrue.s loc_2FC
0x2eb  ldc.i4   0x80060422
0x2f0  ldc.i4.0
0x2f1  newarr   [mscorlib]System.Object
0x2f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2fb  throw
0x2fc  nop
0x2fd  ldarg.0
0x2fe  ldarg.1
0x2ff  ldarg.2
0x300  ldarg.3
0x301  ldstr    aRollup// "Rollup"
0x306  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x30b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.RollupFields.RollupFieldAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x310  call     instance void Microsoft.Crm.Application.WebServices.BusinessRulesWebService::UpdateAttributeRuleDefinition(string ruleAsJson, string entityId, string attributeId, string sourceType, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter ruleAdapter)
0x315  leave.s  loc_33B
0x317  stloc.0
0x318  ldarg.0
0x319  ldloc.0
0x31a  ldarg.3
0x31b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x320  call     instance void Microsoft.Crm.Application.WebServices.BusinessRulesWebService::HandleUpdateAttributeException(class [System.Web.Services]System.Web.Services.Protocols.SoapException ex, valuetype [mscorlib]System.Guid attributeId)
0x325  leave.s  loc_33B
0x327  stloc.1
0x328  ldarg.0
0x329  ldloc.1
0x32a  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::ReturnJsonException(class [mscorlib]System.Exception)
0x32f  ldloc.1
0x330  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x335  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x33a  throw
0x33b  ret
```
