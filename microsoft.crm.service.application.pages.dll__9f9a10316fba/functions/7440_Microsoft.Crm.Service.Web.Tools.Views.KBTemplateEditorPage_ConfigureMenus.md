# Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::ConfigureMenus

- ea: `0x7440`
- end: `0x76bf`
- name: `Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::ConfigureMenus`
- size: `639`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x7440`

## string_xrefs

- `0x74c4`: `<td CLASS="KBTemplateEditorPage_ConfigureMenus_td">`
- `0x74ea`: `TaskBox_Title_CommonTasks`
- `0x7517`: `<table width="100%" cellpadding="0" cellspacing="0" ><tr><td align="center"><img id="imgBtnUp" src="/_imgs/btn_off_up.gif" onmouseover="src='/_imgs/btn_on_up.gif';" onmouseout="src='/_imgs/btn_off_up.gif';" style="cursor:pointer;margin-top:7px" onclick="Move(true);" alt="`
- `0x7525`: `ToolTip_MoveKBSectionUp`
- `0x7537`: `"></td></tr><tr><td height="10"></td></tr><tr><td align="center"><img id="imgBtnDown" src="/_imgs/btn_off_down.gif" onmouseover="src='/_imgs/btn_on_down.gif';" onmouseout="src='/_imgs/btn_off_down.gif';" style="cursor:pointer;" onclick="Move();" alt="`
- `0x7545`: `ToolTip_MoveKBSectionDown`
- `0x7573`: `MenuItem_Templ_Props`
- `0x757d`: `<img alt="" id="imgBtnTemplateProps" src="/_imgs/vieweditor/16_viewProps.gif">`
- `0x7582`: `TemplateProperties();`
- `0x758d`: `Tooltip_Templ_Props`
- `0x75b8`: `Task_Section_Props`
- `0x75c7`: `UpdateSection();`
- `0x75ed`: `Task_Add_A_Section`
- `0x7607`: `Tooltip_Add_Section_Art_Templ`
- `0x7622`: `Task_Remove_Section`
- `0x762c`: `<img alt="" id="imgBtnRemoveSection" src="/_imgs/vieweditor/16_colRemove.gif">`
- `0x7631`: `RemoveSection();`
- `0x763c`: `Tooltip_Remove_Section`

## pseudocode

```c

```

## disassembly

```asm
0x7440  ldarg.0
0x7441  ldfld    bool Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::_isActive
0x7446  brfalse  loc_767B
0x744b  ldarg.0
0x744c  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::editorContent
0x7451  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x7456  ldstr    aTrHeight26Td// "<tr height=\"26\"><td>"
0x745b  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x7460  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x7465  ldarg.0
0x7466  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl::.ctor()
0x746b  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmHtmlBar
0x7470  ldarg.0
0x7471  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmHtmlBar
0x7476  ldc.i4.3
0x7477  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl::set_HeaderType(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType)
0x747c  ldarg.0
0x747d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmHtmlBar
0x7482  ldc.i4.s 0xF
0x7484  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::set_Options(valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar/HtmlBarParam)
0x7489  ldarg.0
0x748a  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::editorContent
0x748f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x7494  ldarg.0
0x7495  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmHtmlBar
0x749a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x749f  ldarg.0
0x74a0  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::editorContent
0x74a5  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x74aa  ldstr    aTdTr// "</td></tr>"
0x74af  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x74b4  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x74b9  ldarg.0
0x74ba  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::taskBoxContent
0x74bf  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x74c4  ldstr    aTdClassKbtempl// "<td CLASS=\"KBTemplateEditorPage_Config"...
0x74c9  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x74ce  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x74d3  ldarg.0
0x74d4  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::.ctor()
0x74d9  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmTaskBox
0x74de  ldarg.0
0x74df  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmTaskBox
0x74e4  ldarg.0
0x74e5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x74ea  ldstr    aTaskboxTitleCo// "TaskBox_Title_CommonTasks"
0x74ef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x74f4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::set_Title(string)
0x74f9  ldarg.0
0x74fa  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmTaskBox
0x74ff  ldstr    a153px// "153px"
0x7504  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::set_Width(string)
0x7509  ldarg.0
0x750a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmTaskBox
0x750f  ldc.i4.5
0x7510  newarr   [mscorlib]System.String
0x7515  dup
0x7516  ldc.i4.0
0x7517  ldstr    aTableWidth100C// "<table width=\"100%\" cellpadding=\"0\""...
0x751c  stelem.ref
0x751d  dup
0x751e  ldc.i4.1
0x751f  ldarg.0
0x7520  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7525  ldstr    aTooltipMovekbs// "ToolTip_MoveKBSectionUp"
0x752a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x752f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x7534  stelem.ref
0x7535  dup
0x7536  ldc.i4.2
0x7537  ldstr    aTdTrTrTdHeight// "\"></td></tr><tr><td height=\"10\"></td"...
0x753c  stelem.ref
0x753d  dup
0x753e  ldc.i4.3
0x753f  ldarg.0
0x7540  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7545  ldstr    aTooltipMovekbs_0// "ToolTip_MoveKBSectionDown"
0x754a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x754f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x7554  stelem.ref
0x7555  dup
0x7556  ldc.i4.4
0x7557  ldstr    aTdTrTableHrSiz// "\"></td></tr></table><hr size=\"1\" sty"...
0x755c  stelem.ref
0x755d  call     string [mscorlib]System.String::Concat(string[])
0x7562  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopHtml(string)
0x7567  ldarg.0
0x7568  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmTaskBox
0x756d  ldarg.0
0x756e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7573  ldstr    aMenuitemTemplP// "MenuItem_Templ_Props"
0x7578  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x757d  ldstr    aImgAltIdImgbtn// "<img alt=\"\" id=\"imgBtnTemplateProps"...
0x7582  ldstr    aTemplateproper// "TemplateProperties();"
0x7587  ldarg.0
0x7588  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x758d  ldstr    aTooltipTemplPr// "Tooltip_Templ_Props"
0x7592  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7597  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x759c  ldarg.0
0x759d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmTaskBox
0x75a2  ldstr    aHrSize1StyleWi// "<hr size=\"1\" style=\"width:130px;colo"...
0x75a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopHtml(string)
0x75ac  ldarg.0
0x75ad  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmTaskBox
0x75b2  ldarg.0
0x75b3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75b8  ldstr    aTaskSectionPro// "Task_Section_Props"
0x75bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75c2  ldstr    aImgAltIdImgbtn_0// "<img alt=\"\" id=\"imgBtnSectionProps\""...
0x75c7  ldstr    aUpdatesection// "UpdateSection();"
0x75cc  ldarg.0
0x75cd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75d2  ldstr    aTooltipSection// "Tooltip_Section_Props"
0x75d7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75dc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x75e1  ldarg.0
0x75e2  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmTaskBox
0x75e7  ldarg.0
0x75e8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75ed  ldstr    aTaskAddASectio// "Task_Add_A_Section"
0x75f2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75f7  ldstr    aImgAltIdImgbtn_1// "<img alt=\"\" id=\"imgBtnAddSection\" s"...
0x75fc  ldstr    aAddsection// "AddSection();"
0x7601  ldarg.0
0x7602  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7607  ldstr    aTooltipAddSect// "Tooltip_Add_Section_Art_Templ"
0x760c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7611  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x7616  ldarg.0
0x7617  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmTaskBox
0x761c  ldarg.0
0x761d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7622  ldstr    aTaskRemoveSect// "Task_Remove_Section"
0x7627  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x762c  ldstr    aImgAltIdImgbtn_2// "<img alt=\"\" id=\"imgBtnRemoveSection"...
0x7631  ldstr    aRemovesection// "RemoveSection();"
0x7636  ldarg.0
0x7637  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x763c  ldstr    aTooltipRemoveS// "Tooltip_Remove_Section"
0x7641  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7646  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x764b  ldarg.0
0x764c  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::taskBoxContent
0x7651  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x7656  ldarg.0
0x7657  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::crmTaskBox
0x765c  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x7661  ldarg.0
0x7662  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::taskBoxContent
0x7667  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x766c  ldstr    aTd// "</td>"
0x7671  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x7676  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x767b  ldarg.0
0x767c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0x7681  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar
0x7686  dup
0x7687  ldarg.0
0x7688  ldftn    instance void Microsoft.Crm.Service.Web.Tools.Views.KBTemplateEditorPage::MenuReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs e)
0x768e  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler::.ctor(object, native int)
0x7693  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_OnMenuReady(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler)
0x7698  dup
0x7699  ldc.i4.s 0x31
0x769b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::RemoveParameter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.FormFileParameters)
0x76a0  dup
0x76a1  ldc.i4.4
0x76a2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::AddParameter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.FormFileParameters)
0x76a7  dup
0x76a8  ldc.i4.2
0x76a9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::AddParameter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.FormActionParameters)
0x76ae  ldarg.0
0x76af  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x76b4  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x76b9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck)
0x76be  ret
```
