# Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::AddRequiredClientScriptFiles

- ea: `0xff8b0`
- end: `0xff9cf`
- name: `Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::AddRequiredClientScriptFiles`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0xff010`

## callees

- `0xfe440`
- `0xfe470`
- `0xfe590`
- `0xfe5a0`
- `0xff8b0`
- `0xff9d0`
- `0xffa10`

## string_xrefs

- `0xff9ae`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xff909`: `/_static/_common/scripts/CommandBarActions.js`
- `0xff8fe`: `/_static/_common/scripts/RibbonActions.js`
- `0xff9b9`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0xff958`: `/_controls/CompositeControl/CompositeControl.css.aspx`
- `0xff914`: `/_static/_controls/GlobalQuickCreate/GlobalQuickCreateBehavior.js`
- `0xff965`: `/_static/_controls/GlobalQuickCreate/GlobalQuickCreateBehavior.js`
- `0xff984`: `/_static/_common/scripts/details.js`
- `0xff8e8`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0xff8f3`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`

## pseudocode

```c

```

## disassembly

```asm
0xff8b0  ldarg.0
0xff8b1  call     instance bool Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::get_IsInlineEditable()
0xff8b6  brfalse  loc_FF976
0xff8bb  ldarg.1
0xff8bc  ldstr    aStaticControls_7// "/_static/_controls/FlyoutDialog/FlyoutD"...
0xff8c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff8c6  ldarg.1
0xff8c7  ldstr    aStaticControls_22// "/_static/_controls/inlineedit/inlineedi"...
0xff8cc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff8d1  ldarg.0
0xff8d2  call     instance bool Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::get_ShowGlobalQuickCreateForm()
0xff8d7  brtrue   loc_FF964
0xff8dc  ldarg.1
0xff8dd  ldstr    aStaticControls_60// "/_static/_controls/notificationlist/not"...
0xff8e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff8e7  ldarg.1
0xff8e8  ldstr    aStaticCommonSc_30// "/_static/_common/scripts/SalesCommonFra"...
0xff8ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff8f2  ldarg.1
0xff8f3  ldstr    aStaticCommonSc_40// "/_static/_common/scripts/SalesCrmSoapPr"...
0xff8f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff8fd  ldarg.1
0xff8fe  ldstr    aStaticCommonSc_8// "/_static/_common/scripts/RibbonActions."...
0xff903  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff908  ldarg.1
0xff909  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/CommandBarActi"...
0xff90e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff913  ldarg.1
0xff914  ldstr    aStaticControls_9// "/_static/_controls/GlobalQuickCreate/Gl"...
0xff919  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff91e  ldarg.0
0xff91f  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::get_FormFactor()
0xff924  ldc.i4.4
0xff925  beq.s    loc_FF957
0xff927  ldarg.0
0xff928  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xff92d  ldstr    aStaticControls_23// "/_static/_controls/ProcessControl/Proce"...
0xff932  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff937  ldarg.0
0xff938  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xff93d  ldstr    aStaticControls_55// "/_static/_controls/InlineEdit/InlineEdi"...
0xff942  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff947  ldarg.0
0xff948  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xff94d  ldstr    aStaticControls_56// "/_static/_controls/ProcessControl/Proce"...
0xff952  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff957  ldarg.1
0xff958  ldstr    aControlsCompos// "/_controls/CompositeControl/CompositeCo"...
0xff95d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xff962  br.s     loc_FF96F
0xff964  ldarg.1
0xff965  ldstr    aStaticControls_9// "/_static/_controls/GlobalQuickCreate/Gl"...
0xff96a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff96f  ldarg.0
0xff970  ldarg.1
0xff971  call     instance void Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::AddResourcesCountryCodeIntegration(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager header)
0xff976  ldarg.0
0xff977  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0xff97c  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_ShowNavigationBar()
0xff981  brfalse.s loc_FF98E
0xff983  ldarg.1
0xff984  ldstr    aStaticCommonSc_24// "/_static/_common/scripts/details.js"
0xff989  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff98e  ldarg.0
0xff98f  call     instance bool Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::get_IsTurboForm()
0xff994  brfalse.s loc_FF9A5
0xff996  ldarg.0
0xff997  call     instance bool Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::get_ShowGlobalQuickCreateForm()
0xff99c  brtrue.s loc_FF9A5
0xff99e  ldarg.0
0xff99f  ldarg.1
0xff9a0  call     instance void Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::AddRibbonLayoutScriptFile(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager header)
0xff9a5  ldarg.0
0xff9a6  call     instance bool Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::get_IsTurboForm()
0xff9ab  brfalse.s loc_FF9CE
0xff9ad  ldarg.1
0xff9ae  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0xff9b3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff9b8  ldarg.1
0xff9b9  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/Mscrm.Caching."...
0xff9be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff9c3  ldarg.1
0xff9c4  ldstr    aStaticFormForm_0// "/_static/form/formcontrols.js"
0xff9c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xff9ce  ret
```
