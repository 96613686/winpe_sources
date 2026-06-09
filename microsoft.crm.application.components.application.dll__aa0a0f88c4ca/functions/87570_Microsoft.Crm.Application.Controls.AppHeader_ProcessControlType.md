# Microsoft.Crm.Application.Controls.AppHeader::ProcessControlType

- ea: `0x87570`
- end: `0x877ca`
- name: `Microsoft.Crm.Application.Controls.AppHeader::ProcessControlType`
- size: `602`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x87570`

## string_xrefs

- `0x875f0`: `/_common/styles/dialogs.css.aspx`
- `0x875a0`: `/_static/_common/scripts/details.js`
- `0x87606`: `/_static/_common/scripts/details.js`
- `0x8764d`: `/_static/_common/scripts/details.js`
- `0x87732`: `/_common/styles/mobile.css`
- `0x8777e`: `/_common/styles/mobile_touchScrolling_Android.css`
- `0x877a3`: `/_common/styles/mobile_touchScrolling.css`
- `0x877bf`: `/_common/styles/mobile_rtl.css`

## pseudocode

```c

```

## disassembly

```asm
0x87570  ldarg.0
0x87571  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppHeader::_appType
0x87576  ldc.i4.2
0x87577  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x8757c  brfalse.s loc_875C0
0x8757e  ldarg.0
0x8757f  ldc.i4   0x2E2
0x87584  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x87589  ldarg.0
0x8758a  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x8758f  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87594  ldarg.0
0x87595  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x8759a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8759f  ldarg.0
0x875a0  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/details.js"
0x875a5  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x875aa  ldarg.0
0x875ab  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x875b0  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x875b5  ldarg.0
0x875b6  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x875bb  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x875c0  ldarg.0
0x875c1  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppHeader::_appType
0x875c6  ldc.i4.8
0x875c7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x875cc  brfalse.s loc_8761C
0x875ce  ldarg.0
0x875cf  ldc.i4   0x80
0x875d4  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x875d9  ldarg.0
0x875da  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x875df  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x875e4  ldarg.0
0x875e5  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x875ea  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x875ef  ldarg.0
0x875f0  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x875f5  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x875fa  ldarg.0
0x875fb  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x87600  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87605  ldarg.0
0x87606  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/details.js"
0x8760b  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87610  ldarg.0
0x87611  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x87616  ldnull
0x87617  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x8761c  ldarg.0
0x8761d  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppHeader::_appType
0x87622  ldc.i4.s 0x10
0x87624  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x87629  brfalse.s loc_87678
0x8762b  ldarg.0
0x8762c  ldc.i4   0x2E2
0x87631  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x87636  ldarg.0
0x87637  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x8763c  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87641  ldarg.0
0x87642  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x87647  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8764c  ldarg.0
0x8764d  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/details.js"
0x87652  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87657  ldarg.0
0x87658  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x8765d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87662  ldarg.0
0x87663  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x87668  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8766d  ldarg.0
0x8766e  ldstr    aStaticActiviti// "/_static/activities/activity.js"
0x87673  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x87678  ldarg.0
0x87679  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppHeader::_appType
0x8767e  ldc.i4   0x80
0x87683  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x87688  brfalse.s loc_876A0
0x8768a  ldarg.0
0x8768b  ldstr    aControlsAttach// "/_controls/attachment/attach.css.aspx"
0x87690  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87695  ldarg.0
0x87696  ldstr    aStaticControls_13// "/_static/_controls/attachment/attachmen"...
0x8769b  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x876a0  ldarg.0
0x876a1  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppHeader::_appType
0x876a6  ldc.i4   0x100
0x876ab  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x876b0  brfalse.s loc_876BD
0x876b2  ldarg.0
0x876b3  ldstr    aControlsNotesN_0// "/_controls/notes/notesprint.css.aspx"
0x876b8  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x876bd  ldarg.0
0x876be  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppHeader::_appType
0x876c3  ldc.i4.s 0x40
0x876c5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x876ca  brfalse.s loc_876D7
0x876cc  ldarg.0
0x876cd  ldstr    aControlsNotesN_1// "/_controls/notes/notectrl.css.aspx"
0x876d2  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x876d7  ldarg.0
0x876d8  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AppControlType Microsoft.Crm.Application.Controls.AppHeader::_appType
0x876dd  ldc.i4   0x400
0x876e2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x876e7  brfalse.s loc_8770A
0x876e9  ldarg.0
0x876ea  ldstr    aWebwizardWizar// "/WebWizard/WizardForm.css.aspx"
0x876ef  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x876f4  ldarg.0
0x876f5  ldstr    aStaticWebwizar// "/_static/webwizard/wizardshare.js"
0x876fa  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x876ff  ldarg.0
0x87700  ldstr    aStaticWebwizar_0// "/_static/webwizard/wizardpage.js"
0x87705  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8770a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x8770f  brfalse.s loc_8771C
0x87711  ldarg.0
0x87712  ldstr    aStyleTypeTextC// "<style type=\"text/css\">.stage {\tback"...
0x87717  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetCustomResource(string)
0x8771c  ldarg.0
0x8771d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.BasicHeader::ProcessControlType()
0x87722  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x87727  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8772c  brfalse  loc_877C9
0x87731  ldarg.0
0x87732  ldstr    aCommonStylesMo// "/_common/styles/mobile.css"
0x87737  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8773c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x87741  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x87746  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetIPadMajorVersion(class [System.Web]System.Web.HttpRequest)
0x8774b  stloc.0
0x8774c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x87751  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x87756  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetIPadMinorVersion(class [System.Web]System.Web.HttpRequest)
0x8775b  stloc.1
0x8775c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x87761  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x87766  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetIPadBuildVersion(class [System.Web]System.Web.HttpRequest)
0x8776b  stloc.2
0x8776c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x87771  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x87776  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsAndroidDevice(class [System.Web]System.Web.HttpRequest)
0x8777b  brfalse.s loc_8778A
0x8777d  ldarg.0
0x8777e  ldstr    aCommonStylesMo_0// "/_common/styles/mobile_touchScrolling_A"...
0x87783  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x87788  br.s     loc_877AD
0x8778a  ldloc.0
0x8778b  ldc.i4.7
0x8778c  bne.un.s loc_877A2
0x8778e  ldloc.0
0x8778f  ldc.i4.7
0x87790  bne.un.s loc_87796
0x87792  ldloc.1
0x87793  ldc.i4.1
0x87794  bgt.s    loc_877A2
0x87796  ldloc.0
0x87797  ldc.i4.7
0x87798  bne.un.s loc_877AD
0x8779a  ldloc.1
0x8779b  ldc.i4.1
0x8779c  bne.un.s loc_877AD
0x8779e  ldloc.2
0x8779f  ldc.i4.2
0x877a0  blt.s    loc_877AD
0x877a2  ldarg.0
0x877a3  ldstr    aCommonStylesMo_1// "/_common/styles/mobile_touchScrolling.c"...
0x877a8  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x877ad  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x877b2  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x877b7  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x877bc  brfalse.s loc_877C9
0x877be  ldarg.0
0x877bf  ldstr    aCommonStylesMo_2// "/_common/styles/mobile_rtl.css"
0x877c4  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x877c9  ret
```
