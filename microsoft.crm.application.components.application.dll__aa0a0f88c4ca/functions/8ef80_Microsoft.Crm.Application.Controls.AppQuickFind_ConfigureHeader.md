# Microsoft.Crm.Application.Controls.AppQuickFind::ConfigureHeader

- ea: `0x8ef80`
- end: `0x8f07f`
- name: `Microsoft.Crm.Application.Controls.AppQuickFind::ConfigureHeader`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8ef00`
- `0x8ef60`

## string_xrefs

- `0x8ef96`: `Web._common.scripts.stage.js_30`
- `0x8efdc`: `/_static/_Common/scripts/Stage.js`
- `0x8f02e`: `/_static/_common/scripts/GlowingImage.js`

## pseudocode

```c

```

## disassembly

```asm
0x8ef80  ldarg.0
0x8ef81  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x8ef86  ldarg.0
0x8ef87  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8ef8c  ldstr    aLocidSearchRes// "LOCID_SEARCH_RESULTS"
0x8ef91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8ef96  ldstr    aWebCommonScrip// "Web._common.scripts.stage.js_30"
0x8ef9b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8efa0  ldc.i4.0
0x8efa1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8efa6  ldarg.0
0x8efa7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8efac  ldstr    aMscrmQuickfind// "Mscrm.QuickFindControl"
0x8efb1  ldarg.0
0x8efb2  call     instance string Microsoft.Crm.Application.Controls.AppQuickFind::get_RenderId()
0x8efb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x8efbc  ldarg.0
0x8efbd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8efc2  ldstr    aStaticGridGrid// "/_static/_grid/GridControl.js"
0x8efc7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8efcc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8efd1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x8efd6  ldarg.0
0x8efd7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8efdc  ldstr    aStaticCommonSc_18// "/_static/_Common/scripts/Stage.js"
0x8efe1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8efe6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8efeb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x8eff0  ldarg.0
0x8eff1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8eff6  ldstr    aStaticControls_4// "/_static/_controls/HintText/HintText.js"
0x8effb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8f000  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8f005  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x8f00a  ldarg.0
0x8f00b  ldstr    aMscrmHinttext// "Mscrm.HintText"
0x8f010  ldnull
0x8f011  ldnull
0x8f012  ldnull
0x8f013  ldarg.0
0x8f014  call     instance string Microsoft.Crm.Application.Controls.AppQuickFind::get_GridId()
0x8f019  ldstr    aFindcriteria// "_findCriteria"
0x8f01e  call     string [mscorlib]System.String::Concat(string, string)
0x8f023  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x8f028  ldarg.0
0x8f029  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8f02e  ldstr    aStaticCommonSc_19// "/_static/_common/scripts/GlowingImage.j"...
0x8f033  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8f038  ldarg.0
0x8f039  ldstr    aMscrmGlowingim// "Mscrm.GlowingImage"
0x8f03e  ldnull
0x8f03f  ldnull
0x8f040  ldnull
0x8f041  ldarg.0
0x8f042  call     instance string Microsoft.Crm.Application.Controls.AppQuickFind::get_GridId()
0x8f047  ldstr    aFindcriteriaim// "_findCriteriaImg"
0x8f04c  call     string [mscorlib]System.String::Concat(string, string)
0x8f051  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x8f056  ldarg.0
0x8f057  ldstr    aMscrmGlowingim// "Mscrm.GlowingImage"
0x8f05c  ldnull
0x8f05d  ldnull
0x8f05e  ldnull
0x8f05f  ldarg.0
0x8f060  call     instance string Microsoft.Crm.Application.Controls.AppQuickFind::get_GridId()
0x8f065  ldstr    aClearcriteriai// "_clearCriteriaImg"
0x8f06a  call     string [mscorlib]System.String::Concat(string, string)
0x8f06f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x8f074  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor()
0x8f079  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x8f07e  ret
```
