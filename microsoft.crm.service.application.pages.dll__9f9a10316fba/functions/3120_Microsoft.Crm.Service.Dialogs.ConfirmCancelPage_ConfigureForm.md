# Microsoft.Crm.Service.Dialogs.ConfirmCancelPage::ConfigureForm

- ea: `0x3120`
- end: `0x3212`
- name: `Microsoft.Crm.Service.Dialogs.ConfirmCancelPage::ConfigureForm`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3120`

## string_xrefs

- `0x313c`: `/_static/_common/styles/AutoToolTip.js`

## pseudocode

```c

```

## disassembly

```asm
0x3120  ldarg.0
0x3121  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x3126  ldarg.0
0x3127  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x312c  ldstr    aStaticCsCasesC// "/_static/cs/cases/cases.js"
0x3131  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3136  ldarg.0
0x3137  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x313c  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x3141  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3146  ldarg.0
0x3147  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x314c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x3151  stloc.0
0x3152  ldloc.0
0x3153  ldc.i4.0
0x3154  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x3159  ldarg.0
0x315a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x315f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3164  ldstr    aReason// "reason"
0x3169  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x316e  ldstr    aNovalidstatust// "novalidstatustransition"
0x3173  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3178  brfalse.s loc_31C4
0x317a  ldarg.0
0x317b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3180  ldarg.0
0x3181  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3186  ldstr    aWebRecordNavig// "Web.Record.NavigateConfirm.Window_Title"
0x318b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3190  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x3195  ldloc.0
0x3196  ldarg.0
0x3197  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x319c  ldstr    aWebCsCasesDlgC_1// "Web._cs.Cases.dlg_ConfirmCancel.aspx_2"
0x31a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x31a6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x31ab  ldloc.0
0x31ac  ldc.i4.1
0x31ad  ldstr    aButtonLabelCon// "Button_Label_Confirm"
0x31b2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x31b7  ldloc.0
0x31b8  ldc.i4.2
0x31b9  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x31be  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x31c3  ret
0x31c4  ldarg.0
0x31c5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x31ca  ldarg.0
0x31cb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x31d0  ldstr    aWebRecordNoval// "Web.Record.NoValidStatusReasonTransitio"...
0x31d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x31da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x31df  ldloc.0
0x31e0  ldarg.0
0x31e1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x31e6  ldstr    aWebRecordNoval// "Web.Record.NoValidStatusReasonTransitio"...
0x31eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x31f0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x31f5  ldarg.0
0x31f6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Service.Dialogs.ConfirmCancelPage::statusMsg
0x31fb  ldstr    aWebRecordNoval_1// "Web.Record.NoValidStatusReasonTransitio"...
0x3200  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x3205  ldloc.0
0x3206  ldc.i4.2
0x3207  ldstr    aButtonLabelOk// "Button_Label_OK"
0x320c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x3211  ret
```
