# Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::ConfigurePage

- ea: `0x10550`
- end: `0x1070b`
- name: `Microsoft.Crm.Service.Application.Pages.Dialogs.CaseHierarchyDialog::ConfigurePage`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x10577`: `/_common/styles/dialogs.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x10550  ldarg.0
0x10551  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x10556  ldarg.0
0x10557  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1055c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x10561  ldarg.0
0x10562  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10567  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0x1056c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x10571  ldarg.0
0x10572  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10577  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x1057c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x10581  ldarg.0
0x10582  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10587  ldstr    aToolsFieldsele// "/_tools/fieldselect/fieldselect.css.asp"...
0x1058c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x10591  ldarg.0
0x10592  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10597  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/objec"...
0x1059c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x105a1  ldarg.0
0x105a2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x105a7  ldstr    aStaticToolsFor_0// "/_static/tools/formeditor/scripts/field"...
0x105ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x105b1  ldarg.0
0x105b2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x105b7  ldstr    aStaticToolsFie// "/_static/_tools/fieldselect/fieldselect"...
0x105bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x105c1  ldarg.0
0x105c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x105c7  ldstr    aStaticToolsVie// "/_static/tools/vieweditor/scripts/selec"...
0x105cc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x105d1  ldarg.0
0x105d2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x105d7  ldstr    aStaticToolsSys// "/_static/tools/systemcustomization/scri"...
0x105dc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x105e1  ldarg.0
0x105e2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x105e7  ldstr    aStaticGridCmds// "/_static/_grid/cmds/multiaction.js"
0x105ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x105f1  ldarg.0
0x105f2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x105f7  ldstr    aLocidSelvalsTi// "LOCID_SELVALS_TITLE_AVAILVALS"
0x105fc  ldarg.0
0x105fd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10602  ldstr    aWebToolsViewed// "Web.Tools.ViewEditor.Dialogs.SelectValu"...
0x10607  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1060c  ldc.i4.0
0x1060d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10612  ldarg.0
0x10613  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10618  ldstr    aLocidSelvalsTi_0// "LOCID_SELVALS_TITLE_SELTDVALS"
0x1061d  ldarg.0
0x1061e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10623  ldstr    aWebToolsViewed_0// "Web.Tools.ViewEditor.Dialogs.SelectValu"...
0x10628  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1062d  ldc.i4.0
0x1062e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10633  ldarg.0
0x10634  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10639  ldstr    aLocidChdCloseP// "LOCID_CHD_CLOSE_PRT_CLOSE"
0x1063e  ldarg.0
0x1063f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10644  ldstr    aWebGridCmdsDlg_0// "Web._grid.cmds.dlg_casehierarchy.aspx_4"
0x10649  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1064e  ldc.i4.0
0x1064f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10654  ldarg.0
0x10655  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1065a  ldstr    aLocidRstrPrtCl// "LOCID_RSTR_PRT_CLOSE"
0x1065f  ldarg.0
0x10660  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10665  ldstr    aWebGridCmdsDlg_1// "Web._grid.cmds.dlg_casehierarchy.aspx_5"
0x1066a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1066f  ldc.i4.0
0x10670  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10675  ldarg.0
0x10676  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1067b  ldstr    aLocidChildCase// "LOCID_CHILD_CASES_SUCCESSFULLY"
0x10680  ldarg.0
0x10681  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10686  ldstr    aWebGridCmdsDlg_2// "Web._grid.cmds.dlg_casehierarchy.aspx_6"
0x1068b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10690  ldc.i4.0
0x10691  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10696  ldarg.0
0x10697  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1069c  ldstr    aLocidAvailable// "LOCID_AVAILABLE_ATTRIBUTES"
0x106a1  ldarg.0
0x106a2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x106a7  ldstr    aWebGridCmdsDlg_3// "Web._grid.cmds.dlg_casehierarchy.aspx_9"
0x106ac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x106b1  ldc.i4.0
0x106b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x106b7  ldarg.0
0x106b8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x106bd  ldstr    aLocidSelectedA// "LOCID_SELECTED_ATTRIBUTES"
0x106c2  ldarg.0
0x106c3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x106c8  ldstr    aWebGridCmdsDlg_4// "Web._grid.cmds.dlg_casehierarchy.aspx_8"
0x106cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x106d2  ldc.i4.0
0x106d3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x106d8  ldarg.0
0x106d9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x106de  ldstr    aLocidCaseHiera// "LOCID_CASE_HIERARACHY_SETTINGS"
0x106e3  ldarg.0
0x106e4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x106e9  ldstr    aWebGridCmdsDlg_5// "Web._grid.cmds.dlg_applycasehierarchy.a"...
0x106ee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x106f3  ldc.i4.0
0x106f4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x106f9  ldarg.0
0x106fa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x106ff  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x10704  ldnull
0x10705  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x1070a  ret
```
