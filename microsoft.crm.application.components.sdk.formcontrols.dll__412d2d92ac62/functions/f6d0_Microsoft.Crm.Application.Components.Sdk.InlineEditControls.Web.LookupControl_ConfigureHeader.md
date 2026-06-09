# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::ConfigureHeader

- ea: `0xf6d0`
- end: `0xf7c5`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::ConfigureHeader`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1450`
- `0x2e40`
- `0x2f20`
- `0x2fc0`
- `0xf6d0`
- `0x106b0`
- `0x10870`
- `0x108c0`

## string_xrefs

- `0xf6ec`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xf6fc`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0xf71c`: `/_static/_forms/linkcontrolbehavior.js`
- `0xf6d6`: `/_common/entityproperties/entitypropertiesutil.js.aspx`
- `0xf7ba`: `/_static/_controls/BreadCrumbControl/BreadCrumbControl.js`

## pseudocode

```c

```

## disassembly

```asm
0xf6d0  ldarg.0
0xf6d1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf6d6  ldstr    aCommonEntitypr// "/_common/entityproperties/entitypropert"...
0xf6db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf6e0  ldarg.0
0xf6e1  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::ConfigureHeader()
0xf6e6  ldarg.0
0xf6e7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf6ec  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/CrmInternalUti"...
0xf6f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf6f6  ldarg.0
0xf6f7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf6fc  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/Mscrm.Caching."...
0xf701  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf706  ldarg.0
0xf707  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf70c  ldstr    aStaticFormsLoo// "/_static/_forms/LookupBehavior.js"
0xf711  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf716  ldarg.0
0xf717  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf71c  ldstr    aStaticFormsLin// "/_static/_forms/linkcontrolbehavior.js"
0xf721  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf726  ldarg.0
0xf727  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf72c  ldstr    aStaticControls_13// "/_static/_controls/partylist/partylist."...
0xf731  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf736  ldarg.0
0xf737  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_LookupStyle()
0xf73c  ldstr    aSubject// "subject"
0xf741  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf746  brfalse.s loc_F755
0xf748  ldarg.0
0xf749  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf74e  call     void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::SetSubjectLookupResources(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager resourceManager)
0xf753  br.s     loc_F7AC
0xf755  ldarg.0
0xf756  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf75b  brfalse.s loc_F7A1
0xf75d  ldarg.0
0xf75e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf763  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0xf768  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_TransactionCurrencyField()
0xf76d  brfalse.s loc_F7A1
0xf76f  ldarg.0
0xf770  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf775  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0xf77a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_TransactionCurrencyField()
0xf77f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xf784  ldarg.0
0xf785  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xf78a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xf78f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf794  brfalse.s loc_F7A1
0xf796  ldarg.0
0xf797  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf79c  call     void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::SetCurrencyResources(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager resourceManager)
0xf7a1  ldarg.0
0xf7a2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf7a7  call     void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::SetLookupResources(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager resourceManager)
0xf7ac  ldarg.0
0xf7ad  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LookupControl::get_ShowAsBreadcrumbControl()
0xf7b2  brfalse.s loc_F7C4
0xf7b4  ldarg.0
0xf7b5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xf7ba  ldstr    aStaticControls_14// "/_static/_controls/BreadCrumbControl/Br"...
0xf7bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf7c4  ret
```
