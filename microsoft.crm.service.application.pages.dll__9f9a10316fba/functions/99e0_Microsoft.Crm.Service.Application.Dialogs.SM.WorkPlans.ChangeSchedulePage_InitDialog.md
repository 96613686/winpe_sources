# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::InitDialog

- ea: `0x99e0`
- end: `0x9a6d`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::InitDialog`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x99e0`

## pseudocode

```c

```

## disassembly

```asm
0x99e0  ldarg.0
0x99e1  ldarg.0
0x99e2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x99e7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x99ec  ldstr    aFormaction// "formaction"
0x99f1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x99f6  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::_formAction
0x99fb  ldarg.0
0x99fc  ldfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::_formAction
0x9a01  brfalse.s loc_9A10
0x9a03  ldarg.0
0x9a04  ldfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::_formAction
0x9a09  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9a0e  brtrue.s loc_9A1B
0x9a10  ldarg.0
0x9a11  ldstr    aEdit_0// "Edit"
0x9a16  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::_formAction
0x9a1b  ldarg.0
0x9a1c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9a21  ldarg.0
0x9a22  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9a27  ldstr    aSmEditWeeklySc// "SM_Edit_Weekly_Schedule"
0x9a2c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x9a36  ldarg.0
0x9a37  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9a3c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x9a41  dup
0x9a42  ldarg.0
0x9a43  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9a48  ldstr    aSmHowToEditSch// "SM_How_To_Edit_Schedule"
0x9a4d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a52  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x9a57  ldarg.0
0x9a58  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9a5d  ldstr    aSmPartOfWeekly// "SM_Part_Of_Weekly_Schedule"
0x9a62  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a67  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x9a6c  ret
```
