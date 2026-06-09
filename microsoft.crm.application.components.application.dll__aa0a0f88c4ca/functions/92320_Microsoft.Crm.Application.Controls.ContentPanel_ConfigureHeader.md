# Microsoft.Crm.Application.Controls.ContentPanel::ConfigureHeader

- ea: `0x92320`
- end: `0x92480`
- name: `Microsoft.Crm.Application.Controls.ContentPanel::ConfigureHeader`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x921b0`
- `0x921d0`
- `0x92210`
- `0x92320`

## string_xrefs

- `0x9240b`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0x923d1`: `/_static/_common/scripts/main.js`
- `0x923b7`: `/_static/_common/scripts/crminternalutility.js`

## pseudocode

```c

```

## disassembly

```asm
0x92320  ldarg.0
0x92321  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x92326  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x9232b  stloc.0
0x9232c  ldloc.0
0x9232d  ldstr    aContenturl// "contentUrl"
0x92332  ldarg.0
0x92333  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Controls.ContentPanel::get_ContentUrl()
0x92338  callvirt instance string [mscorlib]System.Object::ToString()
0x9233d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x92342  ldloc.0
0x92343  ldstr    aTitle// "title"
0x92348  ldarg.0
0x92349  call     instance string Microsoft.Crm.Application.Controls.ContentPanel::get_Title()
0x9234e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x92353  ldloc.0
0x92354  ldstr    aContentareatex// "contentAreaText"
0x92359  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9235e  ldstr    aWebLoaderAspxF// "Web.loader.aspx_frame_stage_alttext"
0x92363  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x92368  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9236d  ldloc.0
0x9236e  ldstr    aDefaulttitle// "defaultTitle"
0x92373  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x92378  ldstr    aMicrosoftCrm// "Microsoft_CRM"
0x9237d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x92382  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x92387  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x9238c  stloc.1
0x9238d  ldloc.1
0x9238e  ldstr    aHistorymanager// "historyManager"
0x92393  ldstr    aCrmhistorymana// "crmHistoryManager"
0x92398  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9239d  ldarg.0
0x9239e  ldstr    aMscrmContentpa// "Mscrm.ContentPanel"
0x923a3  ldloc.0
0x923a4  ldnull
0x923a5  ldloc.1
0x923a6  ldarg.0
0x923a7  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x923ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x923b1  ldarg.0
0x923b2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x923b7  ldstr    aStaticCommonSc_21// "/_static/_common/scripts/crminternaluti"...
0x923bc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x923c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x923c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x923cb  ldarg.0
0x923cc  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x923d1  ldstr    aStaticCommonSc_20// "/_static/_common/scripts/main.js"
0x923d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x923db  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x923e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x923e5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x923ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x923ef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x923f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x923f9  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x923fe  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_UseLegacyFormRendering()
0x92403  brtrue.s loc_92440
0x92405  ldarg.0
0x92406  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9240b  ldstr    aStaticCommonSc_14// "/_static/_common/scripts/Mscrm.Caching."...
0x92410  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x92415  call     class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RestrictedJSForAppLandingPage()
0x9241a  ldstr    aFormcontrols// "FormControls"
0x9241f  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x92424  brtrue.s loc_92440
0x92426  ldarg.0
0x92427  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9242c  ldstr    aStaticFormForm// "/_static/form/formcontrols.js"
0x92431  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x92436  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9243b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x92440  ldarg.0
0x92441  call     instance bool Microsoft.Crm.Application.Controls.ContentPanel::get_DelayLoadContent()
0x92446  brfalse.s loc_9247F
0x92448  ldarg.0
0x92449  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9244e  ldc.i4.1
0x9244f  newarr   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock
0x92454  dup
0x92455  ldc.i4.0
0x92456  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x9245b  dup
0x9245c  ldstr    aStartloadconte// "StartLoadContent"
0x92461  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string)
0x92466  dup
0x92467  ldc.i4.s 0x28
0x92469  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32)
0x9246e  dup
0x9246f  ldstr    aStartloadconte_0// "startLoadContent();"
0x92474  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string)
0x92479  stelem.ref
0x9247a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock[])
0x9247f  ret
```
