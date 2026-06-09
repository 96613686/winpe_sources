# Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::ConfigurePage

- ea: `0x32d0`
- end: `0x3396`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::ConfigurePage`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x32f6`: `/_common/styles/dialogs.css.aspx`
- `0x3317`: `LOCID_NOTEMPLATE_SELECTED`
- `0x3322`: `Alert_Mail_Merge_Template_Must_Be_Supplied`
- `0x3364`: `Alert_Mail_Merge_Template_Retrieve_Failed`

## pseudocode

```c

```

## disassembly

```asm
0x32d0  ldarg.0
0x32d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32d6  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x32db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x32e0  ldarg.0
0x32e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32e6  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x32eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x32f0  ldarg.0
0x32f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32f6  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x32fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x3300  ldarg.0
0x3301  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3306  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x330b  ldnull
0x330c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x3311  ldarg.0
0x3312  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3317  ldstr    aLocidNotemplat// "LOCID_NOTEMPLATE_SELECTED"
0x331c  ldarg.0
0x331d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3322  ldstr    aAlertMailMerge// "Alert_Mail_Merge_Template_Must_Be_Suppl"...
0x3327  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x332c  ldc.i4.0
0x332d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3332  ldarg.0
0x3333  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3338  ldstr    aLocidColumnsSe// "LOCID_COLUMNS_SELECTED"
0x333d  ldarg.0
0x333e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3343  ldstr    aMailmergeButto// "MailMerge_Button_Label_SelectedColumns"
0x3348  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x334d  ldc.i4.0
0x334e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3353  ldarg.0
0x3354  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3359  ldstr    aLocidRetrieveF// "LOCID_RETRIEVE_FAILED"
0x335e  ldarg.0
0x335f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3364  ldstr    aAlertMailMerge_0// "Alert_Mail_Merge_Template_Retrieve_Fail"...
0x3369  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x336e  ldc.i4.0
0x336f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3374  ldarg.0
0x3375  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x337a  ldstr    aLocidMaxcolumn// "LOCID_MAXCOLUMN_ERROR"
0x337f  ldarg.0
0x3380  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3385  ldstr    aAlertMailMerge_1// "Alert_Mail_Merge_MaxColumn_Error"
0x338a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x338f  ldc.i4.0
0x3390  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3395  ret
```
