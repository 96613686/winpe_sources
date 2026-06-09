# Microsoft.Crm.Dialogs.ScriptErrorDetailsDialogPage::ConfigurePage

- ea: `0x1620`
- end: `0x16c2`
- name: `Microsoft.Crm.Dialogs.ScriptErrorDetailsDialogPage::ConfigurePage`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x1631`: `Web__common_error_scriptErrorDetails_aspx_FirstLineOfReport`
- `0x1647`: `Web__common_error_scriptErrorDetails_aspx_Title`

## pseudocode

```c

```

## disassembly

```asm
0x1620  ldarg.0
0x1621  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1626  ldstr    aReportfirstlin// "ReportFirstLine"
0x162b  ldarg.0
0x162c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1631  ldstr    aWebCommonError_2// "Web__common_error_scriptErrorDetails_as"...
0x1636  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x163b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1640  ldarg.0
0x1641  ldarg.0
0x1642  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1647  ldstr    aWebCommonError_3// "Web__common_error_scriptErrorDetails_as"...
0x164c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1651  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x1656  ldarg.0
0x1657  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x165c  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x1661  ldstr    aBtnclose// "btnClose"
0x1666  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x166b  ldstr    aClosewindow// "closeWindow();"
0x1670  ldc.i4.0
0x1671  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0x1676  stloc.0
0x1677  ldloc.0
0x1678  ldarg.0
0x1679  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x167e  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x1683  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1688  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x168d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x1692  ldloc.0
0x1693  ldarg.0
0x1694  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1699  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x169e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16a3  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x16a8  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x16ad  ldarg.0
0x16ae  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x16b3  ldloc.0
0x16b4  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0x16b9  pop
0x16ba  ldarg.0
0x16bb  ldc.i4.0
0x16bc  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_ShowHeader(bool)
0x16c1  ret
```
