# Microsoft.Crm.Dialogs.ErrorDialogPage::ConfigureForm

- ea: `0x10f0`
- end: `0x1221`
- name: `Microsoft.Crm.Dialogs.ErrorDialogPage::ConfigureForm`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10a0`
- `0x10f0`
- `0x1230`
- `0x1270`

## string_xrefs

- `0x11a8`: `butDialogCopy`
- `0x11b2`: `openErrorDetails()`
- `0x1201`: `window.open("`
- `0x1206`: `http://go.microsoft.com/fwlink/p/?LinkID=733684`

## pseudocode

```c

```

## disassembly

```asm
0x10f0  ldarg.0
0x10f1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x10f6  ldarg.0
0x10f7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x10fc  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1101  stloc.0
0x1102  ldloc.0
0x1103  ldc.i4   0x800
0x1108  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x110d  ldarg.0
0x110e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1113  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1118  ldstr    aHresult// "hresult"
0x111d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1122  brfalse.s loc_1164
0x1124  ldarg.0
0x1125  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData Microsoft.Crm.Dialogs.ErrorDialogPage::get_ErrorData()
0x112a  stloc.3
0x112b  ldarg.0
0x112c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Dialogs.ErrorDialogPage::ErrorMessage
0x1131  ldloc.3
0x1132  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_MessageHtml()
0x1137  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x113c  ldarg.0
0x113d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Dialogs.ErrorDialogPage::ErrorTitle
0x1142  ldloc.3
0x1143  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_Title()
0x1148  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x114d  ldarg.0
0x114e  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Dialogs.ErrorDialogPage::ErrorImage
0x1153  ldarg.0
0x1154  ldloc.3
0x1155  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorSeverity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_Severity()
0x115a  call     instance string Microsoft.Crm.Dialogs.ErrorDialogPage::LookupImageUrl(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorSeverity sev)
0x115f  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x1164  ldarg.0
0x1165  call     instance int32 Microsoft.Crm.Dialogs.ErrorDialogPage::GetErrorCodeNumber()
0x116a  stloc.1
0x116b  ldloc.1
0x116c  ldc.i4   0x8005E25A
0x1171  beq.s    loc_1185
0x1173  ldloc.1
0x1174  ldc.i4   0x8005E25B
0x1179  beq.s    loc_1185
0x117b  ldloc.1
0x117c  ldc.i4   0x8005E25C
0x1181  ceq
0x1183  br.s     loc_1186
0x1185  ldc.i4.1
0x1186  stloc.2
0x1187  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x118c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1191  brtrue.s loc_11C5
0x1193  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1198  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x119d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIPhoneDevice(class [System.Web]System.Web.HttpRequest)
0x11a2  brtrue.s loc_11C5
0x11a4  ldloc.2
0x11a5  brtrue.s loc_11C5
0x11a7  ldloc.0
0x11a8  ldstr    aButdialogcopy// "butDialogCopy"
0x11ad  ldstr    aSolutionwizard// "SolutionWizard.Button.Export.Tooltip"
0x11b2  ldstr    aOpenerrordetai// "openErrorDetails()"
0x11b7  ldc.i4.0
0x11b8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool)
0x11bd  ldloc.0
0x11be  ldc.i4.1
0x11bf  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x11c4  ret
0x11c5  ldloc.2
0x11c6  brfalse.s loc_1220
0x11c8  ldloc.1
0x11c9  ldc.i4   0x8005E25C
0x11ce  bne.un.s loc_11EF
0x11d0  ldloc.0
0x11d1  ldc.i4.2
0x11d2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x11d7  ldloc.0
0x11d8  ldstr    aButok// "butOk"
0x11dd  ldstr    aButtonLabelOk// "Button_Label_OK"
0x11e2  ldstr    aResetprofilete// "resetProfileTenantId()"
0x11e7  ldc.i4.0
0x11e8  ldc.i4.1
0x11e9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x11ee  ret
0x11ef  ldloc.0
0x11f0  ldc.i4.1
0x11f1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x11f6  ldloc.0
0x11f7  ldstr    aButdialogtellm// "butDialogTellmeMoreDetails"
0x11fc  ldstr    aSolutionwizard_0// "SolutionWizard.Button.TellMeMoreButton."...
0x1201  ldstr    aWindowOpen// "window.open(\""
0x1206  ldstr    aHttpGoMicrosof// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x120b  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x1210  ldstr    asc_1F7F2// "\");"
0x1215  call     string [mscorlib]System.String::Concat(string, string, string)
0x121a  ldc.i4.0
0x121b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool)
0x1220  ret
```
