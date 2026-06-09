# Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProvisionAll

- ea: `0xd7a0`
- end: `0xd883`
- name: `Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProvisionAll`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd580`

## callees

- `0xd7a0`
- `0xd890`
- `0x52370`

## string_xrefs

- `0xd7ea`: `ProvisionLanguage: MUI pack version '{0}'  is higher than current installed MUI pack version '{1}' => Re-enable language and Reprovision.`
- `0xd806`: `LabelCacheSharingEnabled`
- `0xd837`: `LabelCacheSharingEnabled`
- `0xd85e`: `LabelCacheSharingEnabled`

## pseudocode

```c

```

## disassembly

```asm
0xd7a0  ldarg.1
0xd7a1  ldarg.2
0xd7a2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>::ContainsKey(var<u1>)
0xd7a7  brfalse  loc_D85C
0xd7ac  ldarg.3
0xd7ad  ldarg.2
0xd7ae  ldarg.0
0xd7af  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0xd7b4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xd7b9  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationLanguagePackService::RetrieveVersion(int32, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0xd7be  starg.s  4
0xd7c0  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::GetApplicationVersion()
0xd7c5  stloc.0
0xd7c6  ldarg.s  5
0xd7c8  ldarg.s  4
0xd7ca  ldloc.0
0xd7cb  ldarg.0
0xd7cc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0xd7d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd7d6  call     bool [Microsoft.Crm]Microsoft.Crm.LanguageUtility::IsValidMuiPackVersion(string, string, string, valuetype [mscorlib]System.Guid)
0xd7db  brfalse.s loc_D827
0xd7dd  ldarg.0
0xd7de  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0xd7e3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd7e8  ldc.i4.s 0x18
0xd7ea  ldstr    aProvisionlangu_3// "ProvisionLanguage: MUI pack version '{0"...
0xd7ef  ldc.i4.2
0xd7f0  newarr   [mscorlib]System.Object
0xd7f5  dup
0xd7f6  ldc.i4.0
0xd7f7  ldarg.s  5
0xd7f9  stelem.ref
0xd7fa  dup
0xd7fb  ldc.i4.1
0xd7fc  ldarg.s  4
0xd7fe  stelem.ref
0xd7ff  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd804  ldarg.s  6
0xd806  ldstr    aLabelcacheshar// "LabelCacheSharingEnabled"
0xd80b  ldc.i4.1
0xd80c  box      [mscorlib]System.Boolean
0xd811  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0xd816  ldarg.0
0xd817  ldc.i4.1
0xd818  ldarg.2
0xd819  ldarg.s  5
0xd81b  ldarg.s  4
0xd81d  ldloc.0
0xd81e  ldarg.3
0xd81f  ldarg.s  6
0xd821  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProvisionAllInternal(bool reprovision, int32 language, string versionInMuiPack, string versionInDB, string crmVersion, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationLanguagePackService langService, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0xd826  ret
0xd827  ldarg.s  6
0xd829  ldstr    aVersion_0// "Version"
0xd82e  ldarg.s  4
0xd830  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0xd835  ldarg.s  6
0xd837  ldstr    aLabelcacheshar// "LabelCacheSharingEnabled"
0xd83c  ldc.i4.0
0xd83d  box      [mscorlib]System.Boolean
0xd842  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0xd847  ldarg.3
0xd848  ldarg.s  6
0xd84a  ldarg.0
0xd84b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0xd850  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xd855  ldc.i4.1
0xd856  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationLanguagePackService::Update(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, bool)
0xd85b  ret
0xd85c  ldarg.s  6
0xd85e  ldstr    aLabelcacheshar// "LabelCacheSharingEnabled"
0xd863  ldc.i4.1
0xd864  box      [mscorlib]System.Boolean
0xd869  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0xd86e  ldarg.0
0xd86f  ldc.i4.0
0xd870  ldarg.2
0xd871  ldarg.s  5
0xd873  ldarg.s  4
0xd875  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::GetApplicationVersion()
0xd87a  ldarg.3
0xd87b  ldarg.s  6
0xd87d  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProvisionAllInternal(bool reprovision, int32 language, string versionInMuiPack, string versionInDB, string crmVersion, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationLanguagePackService langService, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0xd882  ret
```
