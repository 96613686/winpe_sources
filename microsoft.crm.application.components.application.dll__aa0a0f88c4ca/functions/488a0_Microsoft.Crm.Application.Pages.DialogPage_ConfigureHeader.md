# Microsoft.Crm.Application.Pages.DialogPage::ConfigureHeader

- ea: `0x488a0`
- end: `0x4896c`
- name: `Microsoft.Crm.Application.Pages.DialogPage::ConfigureHeader`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x45740`
- `0x488a0`
- `0x8d1a0`
- `0x8d7b0`
- `0x8e9d0`
- `0x8e9f0`
- `0x8ea70`
- `0x8eaf0`

## string_xrefs

- `0x4891e`: `/_static/_common/scripts/DialogUtil.js`
- `0x488cc`: `/_common/styles/dialogs.css.aspx`
- `0x488ec`: `/_static/_common/scripts/details.js`

## pseudocode

```c

```

## disassembly

```asm
0x488a0  ldarg.0
0x488a1  call     instance void Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x488a6  ldarg.0
0x488a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x488ac  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x488b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x488b6  ldarg.0
0x488b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x488bc  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x488c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x488c6  ldarg.0
0x488c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x488cc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x488d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x488d6  ldarg.0
0x488d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x488dc  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x488e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x488e6  ldarg.0
0x488e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x488ec  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/details.js"
0x488f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x488f6  ldarg.0
0x488f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x488fc  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x48901  ldnull
0x48902  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x48907  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x4890c  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x48911  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x48916  brfalse.s loc_48928
0x48918  ldarg.0
0x48919  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4891e  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/DialogUtil.js"
0x48923  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x48928  ldarg.0
0x48929  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4892e  ldstr    aLoaddialogargu// "loadDialogArguments"
0x48933  ldstr    aTryIfIsOutlook// "try{if (IS_OUTLOOK_CLIENT && isOutlookH"...
0x48938  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlock(string, string)
0x4893d  ldarg.0
0x4893e  call     instance bool Microsoft.Crm.Application.Controls.DialogBase::get_IsInlined()
0x48943  brfalse.s loc_4896B
0x48945  ldarg.0
0x48946  call     instance bool Microsoft.Crm.Application.Controls.DialogBase::get_OverrideDefaultTabbing()
0x4894b  brtrue.s loc_4895F
0x4894d  ldarg.0
0x4894e  ldarg.0
0x4894f  call     instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x48954  call     int32 Microsoft.Crm.Application.Utility.DialogUtility::GetMaxTabIndexRecursively(class Microsoft.Crm.Application.Forms.AppForm form)
0x48959  stfld    int32 Microsoft.Crm.Application.Pages.DialogPage::_maxTabIndex
0x4895e  ret
0x4895f  ldarg.0
0x48960  ldarg.0
0x48961  call     instance int32 Microsoft.Crm.Application.Controls.DialogBase::get_OverriddenMaxTabIndex()
0x48966  stfld    int32 Microsoft.Crm.Application.Pages.DialogPage::_maxTabIndex
0x4896b  ret
```
