# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::GetEntityMetadata

- ea: `0x630`
- end: `0x684`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::GetEntityMetadata`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x890`
- `0x8d0`
- `0x9c0`

## pseudocode

```c

```

## disassembly

```asm
0x630  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x635  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x63a  ldarg.2
0x63b  ldc.i4.1
0x63c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x641  stloc.0
0x642  ldarg.0
0x643  ldarg.1
0x644  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter Microsoft.Crm.Application.WebServices.BusinessRulesWebService::CreateRuleAdapter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.EditorPageType editorPageType)
0x649  stloc.1
0x64a  ldarg.0
0x64b  ldloc.0
0x64c  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper Microsoft.Crm.Application.WebServices.BusinessRulesWebService::BuildEntityInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x651  stloc.2
0x652  ldarg.0
0x653  ldarg.1
0x654  ldloc.0
0x655  ldloc.1
0x656  call     instance class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper> Microsoft.Crm.Application.WebServices.BusinessRulesWebService::BuildEntityFieldsInfo(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.EditorPageType editorPageType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter ruleAdapter)
0x65b  stloc.3
0x65c  ldloc.2
0x65d  ldloc.3
0x65e  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper>::get_Values()
0x663  call     T0x2B000006
0x668  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityMetadataJsonWrapper::Fields
0x66d  ldstr    aFor// "for(;;);"
0x672  ldloc.2
0x673  ldloc.1
0x674  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter::BuildKnownTypes()
0x679  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>)
0x67e  call     string [mscorlib]System.String::Concat(string, string)
0x683  ret
```
