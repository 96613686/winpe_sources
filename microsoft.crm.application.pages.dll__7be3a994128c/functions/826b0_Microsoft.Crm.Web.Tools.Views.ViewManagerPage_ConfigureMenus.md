# Microsoft.Crm.Web.Tools.Views.ViewManagerPage::ConfigureMenus

- ea: `0x826b0`
- end: `0x82b19`
- name: `Microsoft.Crm.Web.Tools.Views.ViewManagerPage::ConfigureMenus`
- size: `1129`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x81b80`
- `0x81ba0`
- `0x81bc0`
- `0x826b0`
- `0x83d20`

## string_xrefs

- `0x8285f`: `Task_View_CustomControls`
- `0x826cc`: `TaskBox_Title_CommonTasks`
- `0x82731`: `" onclick="Move(true, new Sys.UI.DomEvent(event));" alt="`
- `0x8273f`: `MenuItem_ToolTip_ViewEditor_MoveLeft`
- `0x82783`: ` class ="ms-crm-EditView-LeftRightButtons-On" style="cursor:pointer;" onclick="Move(false, new Sys.UI.DomEvent(event));" alt="`
- `0x82792`: `MenuItem_ToolTip_ViewEditor_MoveRight`
- `0x827b8`: `XUI.Html.DispatchDomEvent(XUI.Html.DomUtils.GetFirstChild(this),XUI.Html.CreateDomEvent('click'))`
- `0x827e4`: `Task_View_Props`
- `0x828c6`: `Task_EdFilter_Criteria`
- `0x82903`: `Task_Config_Sort`
- `0x8290d`: `<img alt="" id="_TConfigSort" src="/_imgs/vieweditor/sort.png">`
- `0x8291d`: `Tooltip_Config_Sort`
- `0x82950`: `Task_Add_View_Cols`
- `0x82987`: `Task_Add_Cols`
- `0x829c4`: `Task_Add_QuickFind_Fields`
- `0x82a09`: `Task_Change_Properties`
- `0x82a3e`: `Task_Remove_Col`
- `0x82a48`: `<img alt="" id="_TRemoveCol" src="/_imgs/vieweditor/colremove.png">`
- `0x82a4d`: `Remove(_oActive);`
- `0x82a58`: `Tooltip_Remove_Col`
- `0x82ab5`: `canbedeleted`
- `0x82acc`: `canbedeleted`

## pseudocode

```c

```

## disassembly

```asm
0x826b0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x826b5  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x826ba  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x826bf  stloc.0
0x826c0  ldarg.0
0x826c1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x826c6  ldarg.0
0x826c7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x826cc  ldstr    aTaskboxTitleCo// "TaskBox_Title_CommonTasks"
0x826d1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x826d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::set_Title(string)
0x826db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x826e0  ldc.i4.s 0xB
0x826e2  newarr   [mscorlib]System.String
0x826e7  dup
0x826e8  ldc.i4.0
0x826e9  ldstr    aTableCellpaddi// "<table cellpadding=\"0\" cellspacing=\""...
0x826ee  stelem.ref
0x826ef  dup
0x826f0  ldc.i4.1
0x826f1  ldloc.0
0x826f2  brtrue.s loc_826FB
0x826f4  ldsfld   string [mscorlib]System.String::Empty
0x826f9  br.s     loc_8270F
0x826fb  ldstr    aThisStyle// "this.style=\""
0x82700  ldstr    aH// "h"
0x82705  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string)
0x8270a  call     string [mscorlib]System.String::Concat(string, string)
0x8270f  stelem.ref
0x82710  dup
0x82711  ldc.i4.2
0x82712  ldstr    aStyleCursorPoi// "\" style=\"cursor:pointer;"
0x82717  stelem.ref
0x82718  dup
0x82719  ldc.i4.3
0x8271a  ldloc.0
0x8271b  brtrue.s loc_82724
0x8271d  ldsfld   string [mscorlib]System.String::Empty
0x82722  br.s     loc_8272E
0x82724  ldstr    aH// "h"
0x82729  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string)
0x8272e  stelem.ref
0x8272f  dup
0x82730  ldc.i4.4
0x82731  ldstr    aOnclickMoveTru// "\" onclick=\"Move(true, new Sys.UI.DomE"...
0x82736  stelem.ref
0x82737  dup
0x82738  ldc.i4.5
0x82739  ldarg.0
0x8273a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8273f  ldstr    aMenuitemToolti_0// "MenuItem_ToolTip_ViewEditor_MoveLeft"
0x82744  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82749  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x8274e  stelem.ref
0x8274f  dup
0x82750  ldc.i4.6
0x82751  ldstr    aATdTdWidth23Td// "\"></a></td><td width=\"23\"></td><td a"...
0x82756  stelem.ref
0x82757  dup
0x82758  ldc.i4.7
0x82759  ldloc.0
0x8275a  brtrue.s loc_82763
0x8275c  ldsfld   string [mscorlib]System.String::Empty
0x82761  br.s     loc_82780
0x82763  ldstr    aStyle_2// " style=\""
0x82768  ldstr    aH// "h"
0x8276d  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string)
0x82772  call     string [mscorlib]System.String::Concat(string, string)
0x82777  dup
0x82778  brtrue.s loc_82780
0x8277a  pop
0x8277b  ldstr    asc_11EF2A// ""
0x82780  stelem.ref
0x82781  dup
0x82782  ldc.i4.8
0x82783  ldstr    aClassMsCrmEdit// " class =\"ms-crm-EditView-LeftRightButt"...
0x82788  stelem.ref
0x82789  dup
0x8278a  ldc.i4.s 9
0x8278c  ldarg.0
0x8278d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82792  ldstr    aMenuitemToolti_1// "MenuItem_ToolTip_ViewEditor_MoveRight"
0x82797  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8279c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x827a1  stelem.ref
0x827a2  dup
0x827a3  ldc.i4.s 0xA
0x827a5  ldstr    aATdTrTableHrSi// "\"></a></td></tr></table><hr size=\"1\""...
0x827aa  stelem.ref
0x827ab  call     string [mscorlib]System.String::Concat(string[])
0x827b0  ldc.i4.1
0x827b1  newarr   [mscorlib]System.Object
0x827b6  dup
0x827b7  ldc.i4.0
0x827b8  ldstr    aXuiHtmlDispatc// "XUI.Html.DispatchDomEvent(XUI.Html.DomU"...
0x827bd  stelem.ref
0x827be  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x827c3  stloc.1
0x827c4  ldarg.0
0x827c5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x827ca  ldloc.1
0x827cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopHtml(string)
0x827d0  ldarg.0
0x827d1  call     instance bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::get_IsFromAdvancedFind()
0x827d6  brtrue.s loc_8280D
0x827d8  ldarg.0
0x827d9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x827de  ldarg.0
0x827df  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x827e4  ldstr    aTaskViewProps// "Task_View_Props"
0x827e9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x827ee  ldstr    aImgAltIdTviewp// "<img alt=\"\" id=\"_TViewProps\" src=\""...
0x827f3  ldstr    aViewproperties// "ViewProperties();"
0x827f8  ldarg.0
0x827f9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x827fe  ldstr    aTooltipViewPro// "Tooltip_View_Props"
0x82803  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82808  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x8280d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x82812  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x82817  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlViewSupport()
0x8281c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x82821  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x82826  brfalse.s loc_82888
0x82828  ldarg.0
0x82829  ldfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isQuickFindView
0x8282e  brtrue.s loc_82888
0x82830  ldarg.0
0x82831  ldfld    int32 Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_queryType
0x82836  ldc.i4.1
0x82837  beq.s    loc_82888
0x82839  ldarg.0
0x8283a  ldfld    int32 Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_queryType
0x8283f  ldc.i4.s 0x40
0x82841  beq.s    loc_82888
0x82843  ldarg.0
0x82844  call     instance bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::get_IsFromTemplateEditor()
0x82849  brtrue.s loc_82888
0x8284b  ldarg.0
0x8284c  call     instance bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::get_IsFromExportToExcelEditor()
0x82851  brtrue.s loc_82888
0x82853  ldarg.0
0x82854  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x82859  ldarg.0
0x8285a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8285f  ldstr    aTaskViewCustom// "Task_View_CustomControls"
0x82864  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82869  ldstr    aImgAltIdTviewc// "<img alt=\"\" id=\"_TViewCustomControls"...
0x8286e  ldstr    aViewcustomcont// "ViewCustomControlProperties();"
0x82873  ldarg.0
0x82874  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82879  ldstr    aTooltipViewCus// "Tooltip_View_CustomControls"
0x8287e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82883  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x82888  ldarg.0
0x82889  ldfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isSystemView
0x8288e  brfalse.s loc_828EF
0x82890  ldarg.0
0x82891  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x82896  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_DataXml()
0x8289b  ldstr    aQueryapi// "queryapi"
0x828a0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x828a5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x828aa  brtrue.s loc_828EF
0x828ac  ldarg.0
0x828ad  ldarg.0
0x828ae  ldfld    string Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_fetchXml
0x828b3  call     instance bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::IsFilterEditingSupported(string fetch)
0x828b8  brfalse.s loc_828EF
0x828ba  ldarg.0
0x828bb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x828c0  ldarg.0
0x828c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x828c6  ldstr    aTaskEdfilterCr// "Task_EdFilter_Criteria"
0x828cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x828d0  ldstr    aImgAltIdTedfil// "<img alt=\"\" id=\"_TEdFilterCriteria\""...
0x828d5  ldstr    aFilter_1// "Filter();"
0x828da  ldarg.0
0x828db  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x828e0  ldstr    aTooltipEdfilte// "Tooltip_EdFilter_Criteria"
0x828e5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x828ea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x828ef  ldarg.0
0x828f0  call     instance bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::get_IsFromTemplateEditor()
0x828f5  brtrue.s loc_8293C
0x828f7  ldarg.0
0x828f8  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x828fd  ldarg.0
0x828fe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82903  ldstr    aTaskConfigSort// "Task_Config_Sort"
0x82908  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8290d  ldstr    aImgAltIdTconfi// "<img alt=\"\" id=\"_TConfigSort\" src="...
0x82912  ldstr    aSetsort// "SetSort();"
0x82917  ldarg.0
0x82918  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8291d  ldstr    aTooltipConfigS// "Tooltip_Config_Sort"
0x82922  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82927  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x8292c  ldarg.0
0x8292d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x82932  ldstr    aHrSize1StyleWi// "<hr size=\"1\" style=\"width:120px;colo"...
0x82937  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopHtml(string)
0x8293c  ldarg.0
0x8293d  ldfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isQuickFindView
0x82942  brfalse.s loc_8297B
0x82944  ldarg.0
0x82945  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x8294a  ldarg.0
0x8294b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82950  ldstr    aTaskAddViewCol// "Task_Add_View_Cols"
0x82955  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8295a  ldstr    aImgAltIdTaddvi// "<img alt=\"\" id=\"_TAddViewCols\" src="...
0x8295f  ldstr    aAddcolumnsOact// "AddColumns(_oActive, true);"
0x82964  ldarg.0
0x82965  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8296a  ldstr    aTooltipAddCols// "Tooltip_Add_Cols"
0x8296f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82974  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x82979  br.s     loc_829B0
0x8297b  ldarg.0
0x8297c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x82981  ldarg.0
0x82982  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82987  ldstr    aTaskAddCols// "Task_Add_Cols"
0x8298c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82991  ldstr    aImgAltIdTaddco// "<img alt=\"\" id=\"_TAddCols\" src=\"/_"...
0x82996  ldstr    aAddcolumnsOact_0// "AddColumns(_oActive, false);"
0x8299b  ldarg.0
0x8299c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x829a1  ldstr    aTooltipAddCols// "Tooltip_Add_Cols"
0x829a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x829ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x829b0  ldarg.0
0x829b1  ldfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isQuickFindView
0x829b6  brfalse.s loc_829ED
0x829b8  ldarg.0
0x829b9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x829be  ldarg.0
0x829bf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x829c4  ldstr    aTaskAddQuickfi// "Task_Add_QuickFind_Fields"
0x829c9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x829ce  ldstr    aImgAltIdTaddqu// "<img alt=\"\" id=\"_TAddQuickFindFields"...
0x829d3  ldstr    aEditquickfindf// "EditQuickFindFields();"
0x829d8  ldarg.0
0x829d9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x829de  ldstr    aTooltipEditQui// "Tooltip_Edit_QuickFind_Fields"
0x829e3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x829e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x829ed  ldarg.0
0x829ee  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x829f3  ldstr    aHrSize1StyleWi// "<hr size=\"1\" style=\"width:120px;colo"...
0x829f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopHtml(string)
0x829fd  ldarg.0
0x829fe  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x82a03  ldarg.0
0x82a04  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82a09  ldstr    aTaskChangeProp// "Task_Change_Properties"
0x82a0e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82a13  ldstr    aImgAltIdTchang// "<img alt=\"\" id=\"_TChangeProperties\""...
0x82a18  ldstr    aColumnproperti// "ColumnProperties(_oActive);"
0x82a1d  ldarg.0
0x82a1e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82a23  ldstr    aTooltipChangeP// "Tooltip_Change_Props_Col"
0x82a28  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82a2d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x82a32  ldarg.0
0x82a33  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Tools.Views.ViewManagerPage::crmTaskBox
0x82a38  ldarg.0
0x82a39  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82a3e  ldstr    aTaskRemoveCol// "Task_Remove_Col"
0x82a43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82a48  ldstr    aImgAltIdTremov// "<img alt=\"\" id=\"_TRemoveCol\" src=\""...
0x82a4d  ldstr    aRemoveOactive// "Remove(_oActive);"
0x82a52  ldarg.0
0x82a53  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x82a58  ldstr    aTooltipRemoveC// "Tooltip_Remove_Col"
0x82a5d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82a62  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string)
0x82a67  ldarg.0
0x82a68  ldfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isSystemView
0x82a6d  brfalse  loc_82B18
0x82a72  ldarg.0
0x82a73  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0x82a78  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar
0x82a7d  stloc.2
0x82a7e  ldloc.2
0x82a7f  ldarg.0
0x82a80  ldftn    instance void Microsoft.Crm.Web.Tools.Views.ViewManagerPage::MenuReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs e)
0x82a86  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler::.ctor(object, native int)
0x82a8b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_OnMenuReady(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler)
0x82a90  ldloc.2
0x82a91  ldc.i4   0x131
0x82a96  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::RemoveParameter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.FormFileParameters)
0x82a9b  ldloc.2
0x82a9c  ldc.i4.4
0x82a9d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::AddParameter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.FormFileParameters)
0x82aa2  ldarg.0
0x82aa3  ldfld    bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::_isCustomizable
0x82aa8  brfalse.s loc_82AF4
0x82aaa  ldarg.0
  ... truncated ...
```
