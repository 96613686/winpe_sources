# Microsoft.Crm.Application.Controls.AppFooter::ProcessControlType

- ea: `0x87c20`
- end: `0x87dd3`
- name: `Microsoft.Crm.Application.Controls.AppFooter::ProcessControlType`
- size: `435`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x87c20`

## string_xrefs

- `0x87ca0`: `/_common/styles/dialogs.css.aspx`
- `0x87c50`: `/_static/_common/scripts/details.js`
- `0x87cb6`: `/_static/_common/scripts/details.js`
- `0x87cfd`: `/_static/_common/scripts/details.js`

## pseudocode

```c

```

## disassembly

```asm
0x87c20  ldarg.0
0x87c21  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppFooter::_appType
0x87c26  ldc.i4.2
0x87c27  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x87c2c  brfalse.s loc_87C70
0x87c2e  ldarg.0
0x87c2f  ldc.i4   0x2E2
0x87c34  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x87c39  ldarg.0
0x87c3a  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x87c3f  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87c44  ldarg.0
0x87c45  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x87c4a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87c4f  ldarg.0
0x87c50  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/details.js"
0x87c55  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87c5a  ldarg.0
0x87c5b  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x87c60  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87c65  ldarg.0
0x87c66  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x87c6b  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87c70  ldarg.0
0x87c71  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppFooter::_appType
0x87c76  ldc.i4.8
0x87c77  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x87c7c  brfalse.s loc_87CCC
0x87c7e  ldarg.0
0x87c7f  ldc.i4   0x80
0x87c84  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x87c89  ldarg.0
0x87c8a  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x87c8f  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87c94  ldarg.0
0x87c95  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x87c9a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87c9f  ldarg.0
0x87ca0  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x87ca5  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87caa  ldarg.0
0x87cab  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x87cb0  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87cb5  ldarg.0
0x87cb6  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/details.js"
0x87cbb  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87cc0  ldarg.0
0x87cc1  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x87cc6  ldnull
0x87cc7  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x87ccc  ldarg.0
0x87ccd  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppFooter::_appType
0x87cd2  ldc.i4.s 0x10
0x87cd4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x87cd9  brfalse.s loc_87D28
0x87cdb  ldarg.0
0x87cdc  ldc.i4   0x2E2
0x87ce1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x87ce6  ldarg.0
0x87ce7  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x87cec  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87cf1  ldarg.0
0x87cf2  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x87cf7  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87cfc  ldarg.0
0x87cfd  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/details.js"
0x87d02  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87d07  ldarg.0
0x87d08  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x87d0d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87d12  ldarg.0
0x87d13  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x87d18  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87d1d  ldarg.0
0x87d1e  ldstr    aStaticActiviti// "/_static/activities/activity.js"
0x87d23  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87d28  ldarg.0
0x87d29  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppFooter::_appType
0x87d2e  ldc.i4   0x80
0x87d33  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x87d38  brfalse.s loc_87D50
0x87d3a  ldarg.0
0x87d3b  ldstr    aControlsAttach// "/_controls/attachment/attach.css.aspx"
0x87d40  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87d45  ldarg.0
0x87d46  ldstr    aStaticControls_13// "/_static/_controls/attachment/attachmen"...
0x87d4b  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87d50  ldarg.0
0x87d51  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppFooter::_appType
0x87d56  ldc.i4   0x100
0x87d5b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x87d60  brfalse.s loc_87D6D
0x87d62  ldarg.0
0x87d63  ldstr    aControlsNotesN_0// "/_controls/notes/notesprint.css.aspx"
0x87d68  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87d6d  ldarg.0
0x87d6e  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppFooter::_appType
0x87d73  ldc.i4.s 0x40
0x87d75  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x87d7a  brfalse.s loc_87D87
0x87d7c  ldarg.0
0x87d7d  ldstr    aControlsNotesN_1// "/_controls/notes/notectrl.css.aspx"
0x87d82  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87d87  ldarg.0
0x87d88  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppFooter::_appType
0x87d8d  ldc.i4   0x400
0x87d92  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x87d97  brfalse.s loc_87DBA
0x87d99  ldarg.0
0x87d9a  ldstr    aWebwizardWizar// "/WebWizard/WizardForm.css.aspx"
0x87d9f  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87da4  ldarg.0
0x87da5  ldstr    aStaticWebwizar// "/_static/webwizard/wizardshare.js"
0x87daa  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87daf  ldarg.0
0x87db0  ldstr    aStaticWebwizar_0// "/_static/webwizard/wizardpage.js"
0x87db5  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87dba  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x87dbf  brfalse.s loc_87DCC
0x87dc1  ldarg.0
0x87dc2  ldstr    aStyleTypeTextC// "<style type=\"text/css\">.stage {\tback"...
0x87dc7  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetCustomResource(string)
0x87dcc  ldarg.0
0x87dcd  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::ProcessControlType()
0x87dd2  ret
```
