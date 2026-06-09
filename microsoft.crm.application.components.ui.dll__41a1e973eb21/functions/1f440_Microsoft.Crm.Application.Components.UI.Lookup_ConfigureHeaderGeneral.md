# Microsoft.Crm.Application.Components.UI.Lookup::ConfigureHeaderGeneral

- ea: `0x1f440`
- end: `0x1f5b5`
- name: `Microsoft.Crm.Application.Components.UI.Lookup::ConfigureHeaderGeneral`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f3f0`

## callees

- `0x3380`
- `0x38d0`
- `0x39f0`
- `0x1f2c0`
- `0x1f440`
- `0x1ffc0`
- `0x23b60`
- `0x23c50`

## string_xrefs

- `0x1f446`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x1f456`: `/_static/_common/scripts/Mscrm.Caching.js`

## pseudocode

```c

```

## disassembly

```asm
0x1f440  ldarg.0
0x1f441  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f446  ldstr    aStaticCommonSc_45// "/_static/_common/scripts/CrmInternalUti"...
0x1f44b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1f450  ldarg.0
0x1f451  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f456  ldstr    aStaticCommonSc_46// "/_static/_common/scripts/Mscrm.Caching."...
0x1f45b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1f460  ldarg.0
0x1f461  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f466  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0x1f46b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1f470  ldarg.0
0x1f471  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f476  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x1f47b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x1f480  ldarg.0
0x1f481  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f486  ldstr    aStaticFormsLoo_1// "/_static/_Forms/LookupBehavior.js"
0x1f48b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x1f490  ldarg.0
0x1f491  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f496  ldstr    aLocidLuSelectV// "LOCID_LU_SELECT_VALUE_FOR"
0x1f49b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f4a0  ldstr    aWebFormsStyles_3// "Web._forms.styles.IMG.lu.htc_38"
0x1f4a5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f4aa  ldc.i4.0
0x1f4ab  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f4b0  ldarg.0
0x1f4b1  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f4b6  ldstr    aLocidLuSelectV_0// "LOCID_LU_SELECT_VALUE"
0x1f4bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f4c0  ldstr    aWebFormsStyles_4// "Web._forms.styles.IMG.lu.htc_46"
0x1f4c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f4ca  ldc.i4.0
0x1f4cb  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f4d0  ldarg.0
0x1f4d1  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f4d6  ldstr    aLocidLuErrorRe// "LOCID_LU_ERROR_RESOLVED"
0x1f4db  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f4e0  ldstr    aWebFormStylesI// "Web._form.styles.IMG.lu.htc_ResolveErro"...
0x1f4e5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f4ea  ldc.i4.0
0x1f4eb  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f4f0  ldarg.0
0x1f4f1  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f4f6  ldstr    aLocidLuMsgHasu// "LOCID_LU_MSG_HASUNRESOLVEDITEMS"
0x1f4fb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f500  ldstr    aWebFormStylesI_0// "Web._form.styles.IMG.lu.htc_MsgHasUnres"...
0x1f505  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f50a  ldc.i4.0
0x1f50b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f510  ldarg.0
0x1f511  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f516  ldstr    aLocidLuLookupu// "LOCID_LU_LOOKUPUNRESOLVEDTOOLTIP"
0x1f51b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f520  ldstr    aLookupunresolv// "LookupUnresolvedTooltip"
0x1f525  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f52a  ldc.i4.0
0x1f52b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f530  ldarg.0
0x1f531  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1f536  ldstr    aLocidLuLookupa// "LOCID_LU_LOOKUPAMBIGUOUSTOOLTIP"
0x1f53b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f540  ldstr    aLookupambiguou// "LookupAmbiguousTooltip"
0x1f545  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f54a  ldc.i4.0
0x1f54b  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1f550  ldarg.0
0x1f551  call     instance bool Microsoft.Crm.Application.Components.UI.Lookup::get_UseTouchSkin()
0x1f556  brtrue.s loc_1F579
0x1f558  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1f55d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1f562  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OrionAir()
0x1f567  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f56c  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f571  brfalse.s loc_1F579
0x1f573  ldarg.0
0x1f574  call     instance void Microsoft.Crm.Application.Components.UI.Lookup::SetLookupResources()
0x1f579  ldarg.0
0x1f57a  ldfld    class Microsoft.Crm.Application.Components.UI.LookupItemCollection Microsoft.Crm.Application.Components.UI.Lookup::_items
0x1f57f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1f584  stloc.0
0x1f585  br.s     loc_1F599
0x1f587  ldloc.0
0x1f588  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f58d  castclass Microsoft.Crm.Application.Components.UI.LookupItem
0x1f592  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x1f597  leave.s  loc_1F5B4
0x1f599  ldloc.0
0x1f59a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f59f  brtrue.s loc_1F587
0x1f5a1  leave.s  loc_1F5B4
0x1f5a3  ldloc.0
0x1f5a4  isinst   [mscorlib]System.IDisposable
0x1f5a9  stloc.1
0x1f5aa  ldloc.1
0x1f5ab  brfalse.s loc_1F5B3
0x1f5ad  ldloc.1
0x1f5ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f5b3  endfinally
0x1f5b4  ret
```
