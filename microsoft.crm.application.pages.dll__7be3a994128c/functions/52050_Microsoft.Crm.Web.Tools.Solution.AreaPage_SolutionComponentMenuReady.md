# Microsoft.Crm.Web.Tools.Solution.AreaPage::SolutionComponentMenuReady

- ea: `0x52050`
- end: `0x52be0`
- name: `Microsoft.Crm.Web.Tools.Solution.AreaPage::SolutionComponentMenuReady`
- size: `2960`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x52000`
- `0x52050`
- `0x52be0`
- `0x532e0`
- `0x537b0`
- `0x537d0`

## string_xrefs

- `0x52175`: `/_imgs/ico_16_delete.gif`
- `0x5215a`: `MenuItem_Label_Delete_SolutionCompontent`
- `0x5216a`: `Mscrm.SolutionComponentList.deleteSolutionComponent()`
- `0x52190`: `MenuItem_Label_Delete_SolutionCompontent_ToolTip`
- `0x521a0`: `_MBDeleteSolutionComponent`
- `0x52208`: `MenuItem_Label_Remove_SolutionCompontent`
- `0x52220`: `Mscrm.SolutionComponentList.removeSolutionSubcomponent(`
- `0x52241`: `Mscrm.SolutionComponentList.removeSolutionComponent()`
- `0x5224c`: `/_imgs/solution/removecomponent.gif`
- `0x52267`: `MenuItem_Label_Remove_SolutionCompontent_ToolTip`
- `0x52277`: `_MBRemoveSolutionComponent`
- `0x52308`: `MenuItem_Label_AddSubcomponents`
- `0x5239f`: `MenuItem_Label_AddSubcomponents`
- `0x523f0`: `MenuItem_Label_AddSubcomponents`
- `0x52426`: `MenuItem_Label_AddSubcomponents`
- `0x5231a`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0x5238f`: `/_imgs/solution/addrequiredcomponents.gif`
- `0x5240b`: `/_imgs/solution/addrequiredcomponents.gif`
- `0x52756`: `/_imgs/solution/addrequiredcomponents.gif`
- `0x523a9`: `btnAddSubcomponents`
- `0x52400`: `Mscrm.SolutionComponentList.callPerformActionAfterSelectSubcomponent()`
- `0x52436`: `_MBAddSubcomponents`
- `0x524ad`: `Mscrm.SolutionComponentList.publishSolutionComponent()`
- `0x525ab`: `Mscrm.SolutionComponentList.publishSolutionComponent()`
- `0x524e3`: `_MBPublishSolutionComponents`
- `0x525e1`: `_MBPublishSolutionComponents`
- `0x5252b`: `Mscrm.SolutionComponentList.unPublishSolutionComponent()`
- `0x52561`: `_MBUnPublishSolutionComponents`
- `0x525d1`: `MenuItem_Label_PublishSolutionComponents_Tooltip`
- `0x5262d`: `Mscrm.SolutionComponentList.showComponentDependency()`
- `0x526bc`: `Mscrm.SolutionComponentList.editSolutionComponent()`
- `0x526e2`: `MenuItem_Label_EditSolutionComponents_Tooltip`
- `0x5274b`: `Mscrm.SolutionComponentList.addComponentDependency()`
- `0x527da`: `Mscrm.SolutionComponentList.launchManagedProperties()`
- `0x5287a`: `MenuItem_Label_ConfigureRelevanceSearch`
- `0x528b0`: `MenuItem_Label_ConfigureRelevanceSearch`
- `0x5288a`: `Mscrm.SolutionComponentList.launchRelevanceSearchConfiguration()`
- `0x528c0`: `_MBConfigureRelevanceSearch`
- `0x52957`: `Mscrm.SolutionComponentList.assignDashboardRoles();`
- `0x529d9`: `Mscrm.SolutionComponentList.setDefaultDashboard()`
- `0x52a68`: `Mscrm.SolutionComponentList.saveAsDashboard()`

## pseudocode

```c

```

## disassembly

```asm
0x52050  ldarg.0
0x52051  ldarg.1
0x52052  ldarg.2
0x52053  call     instance void Microsoft.Crm.Web.Tools.Solution.AreaPage::HideMenuControls(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs e)
0x52058  ldarg.0
0x52059  call     instance bool Microsoft.Crm.Web.Tools.Solution.AreaPage::IsManaged()
0x5205e  brtrue.s loc_52068
0x52060  ldarg.0
0x52061  ldfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isMetadataDrivenDialogForm
0x52066  brfalse.s loc_5208A
0x52068  ldarg.0
0x52069  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x5206e  brfalse.s loc_5208A
0x52070  ldarg.0
0x52071  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x52076  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x5207b  ldstr    aDisabledblclic// "disableDblClick"
0x52080  ldstr    a1// "1"
0x52085  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x5208a  ldarg.0
0x5208b  call     instance bool Microsoft.Crm.Web.Tools.Solution.AreaPage::IsManaged()
0x52090  brfalse.s loc_52093
0x52092  ret
0x52093  ldc.i4.0
0x52094  stloc.0
0x52095  ldarg.0
0x52096  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter Microsoft.Crm.Web.Tools.Solution.AreaPage::selectedFilter
0x5209b  brfalse.s loc_520A9
0x5209d  ldarg.0
0x5209e  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter Microsoft.Crm.Web.Tools.Solution.AreaPage::selectedFilter
0x520a3  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32)
0x520a8  stloc.0
0x520a9  ldnull
0x520aa  stloc.1
0x520ab  ldarg.0
0x520ac  ldfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isMetadataDrivenDialogForm
0x520b1  brtrue.s loc_5210F
0x520b3  ldloc.0
0x520b4  ldc.i4   0x2619
0x520b9  beq.s    loc_5210F
0x520bb  ldarg.0
0x520bc  ldfld    int32 Microsoft.Crm.Web.Tools.Solution.AreaPage::entityTypeCode
0x520c1  ldc.i4.m1
0x520c2  beq.s    loc_520F7
0x520c4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x520c9  ldarg.0
0x520ca  ldfld    int32 Microsoft.Crm.Web.Tools.Solution.AreaPage::entityTypeCode
0x520cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x520d4  stloc.1
0x520d5  ldloc.1
0x520d6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanCreateForms()
0x520db  brfalse.s loc_5210F
0x520dd  ldarg.0
0x520de  ldarg.2
0x520df  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x520e4  ldc.i4.0
0x520e5  call     instance void Microsoft.Crm.Web.Tools.Solution.AreaPage::BuildAddComponentsMenu(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar menuBar, valuetype Microsoft.Crm.Web.Tools.Solution.ActionType actionType)
0x520ea  ldarg.2
0x520eb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x520f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x520f5  br.s     loc_5210F
0x520f7  ldarg.0
0x520f8  ldarg.2
0x520f9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x520fe  ldc.i4.0
0x520ff  call     instance void Microsoft.Crm.Web.Tools.Solution.AreaPage::BuildAddComponentsMenu(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar menuBar, valuetype Microsoft.Crm.Web.Tools.Solution.ActionType actionType)
0x52104  ldarg.2
0x52105  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x5210a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x5210f  ldarg.0
0x52110  call     instance bool Microsoft.Crm.Web.Tools.Solution.AreaPage::IsDefaultSolution()
0x52115  brtrue.s loc_5212F
0x52117  ldarg.0
0x52118  ldarg.2
0x52119  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x5211e  ldc.i4.1
0x5211f  call     instance void Microsoft.Crm.Web.Tools.Solution.AreaPage::BuildAddComponentsMenu(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar menuBar, valuetype Microsoft.Crm.Web.Tools.Solution.ActionType actionType)
0x52124  ldarg.2
0x52125  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x5212a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x5212f  ldarg.0
0x52130  ldloc.0
0x52131  ldc.i4.3
0x52132  call     instance bool Microsoft.Crm.Web.Tools.Solution.AreaPage::EnableActionType(int32 typeCode, valuetype Microsoft.Crm.Web.Tools.Solution.ActionType actionType)
0x52137  brfalse.s loc_521B0
0x52139  ldarg.2
0x5213a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x5213f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x52144  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x52149  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x5214e  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x52153  dup
0x52154  ldarg.0
0x52155  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5215a  ldstr    aMenuitemLabelD_3// "MenuItem_Label_Delete_SolutionComponten"...
0x5215f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x52164  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x52169  dup
0x5216a  ldstr    aMscrmSolutionc// "Mscrm.SolutionComponentList.deleteSolut"...
0x5216f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x52174  dup
0x52175  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0x5217a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5217f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52184  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x52189  dup
0x5218a  ldarg.0
0x5218b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x52190  ldstr    aMenuitemLabelD_4// "MenuItem_Label_Delete_SolutionComponten"...
0x52195  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5219a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x5219f  dup
0x521a0  ldstr    aMbdeletesoluti// "_MBDeleteSolutionComponent"
0x521a5  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x521aa  ldc.i4.1
0x521ab  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x521b0  ldarg.0
0x521b1  ldfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isEntityDashboard
0x521b6  brfalse.s loc_521CE
0x521b8  ldarg.0
0x521b9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x521be  ldloc.1
0x521bf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x521c4  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0x521c9  brfalse  loc_52288
0x521ce  ldarg.0
0x521cf  ldloc.0
0x521d0  ldc.i4.4
0x521d1  call     instance bool Microsoft.Crm.Web.Tools.Solution.AreaPage::EnableActionType(int32 typeCode, valuetype Microsoft.Crm.Web.Tools.Solution.ActionType actionType)
0x521d6  brfalse  loc_52288
0x521db  ldarg.2
0x521dc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x521e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x521e6  ldarg.2
0x521e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x521ec  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x521f1  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x521f6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x521fb  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x52200  stloc.2
0x52201  ldloc.2
0x52202  ldarg.0
0x52203  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x52208  ldstr    aMenuitemLabelR_0// "MenuItem_Label_Remove_SolutionComponten"...
0x5220d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x52212  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x52217  ldarg.0
0x52218  ldfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isEntityDashboard
0x5221d  brfalse.s loc_52240
0x5221f  ldloc.2
0x52220  ldstr    aMscrmSolutionc_0// "Mscrm.SolutionComponentList.removeSolut"...
0x52225  ldc.i4   0x2704
0x5222a  box      [mscorlib]System.Int32
0x5222f  ldstr    asc_14E862// ")"
0x52234  call     string [mscorlib]System.String::Concat(object, object, object)
0x52239  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x5223e  br.s     loc_5224B
0x52240  ldloc.2
0x52241  ldstr    aMscrmSolutionc_1// "Mscrm.SolutionComponentList.removeSolut"...
0x52246  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x5224b  ldloc.2
0x5224c  ldstr    aImgsSolutionRe// "/_imgs/solution/removecomponent.gif"
0x52251  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x52256  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5225b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x52260  ldloc.2
0x52261  ldarg.0
0x52262  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x52267  ldstr    aMenuitemLabelR_1// "MenuItem_Label_Remove_SolutionComponten"...
0x5226c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x52271  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x52276  ldloc.2
0x52277  ldstr    aMbremovesoluti// "_MBRemoveSolutionComponent"
0x5227c  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x52281  ldloc.2
0x52282  ldc.i4.1
0x52283  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x52288  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x5228d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x52292  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SolutionSegmentation()
0x52297  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5229c  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x522a1  brfalse  loc_52446
0x522a6  ldarg.0
0x522a7  call     instance bool Microsoft.Crm.Web.Tools.Solution.AreaPage::IsManaged()
0x522ac  brtrue   loc_52446
0x522b1  ldarg.0
0x522b2  call     instance bool Microsoft.Crm.Web.Tools.Solution.AreaPage::IsDefaultSolution()
0x522b7  brtrue   loc_52446
0x522bc  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteCustomization()
0x522c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x522c6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x522cb  brfalse  loc_52446
0x522d0  ldarg.0
0x522d1  ldfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isEntityDashboard
0x522d6  brfalse  loc_523B9
0x522db  ldarg.0
0x522dc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x522e1  ldloc.1
0x522e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x522e7  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0x522ec  brfalse  loc_523B9
0x522f1  ldarg.2
0x522f2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x522f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x522fc  ldarg.2
0x522fd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x52302  ldarg.0
0x52303  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x52308  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0x5230d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x52312  ldc.i4.7
0x52313  newarr   [mscorlib]System.Object
0x52318  dup
0x52319  ldc.i4.0
0x5231a  ldstr    aMscrmSolutionc_2// "Mscrm.SolutionComponentList.manageSelec"...
0x5231f  stelem.ref
0x52320  dup
0x52321  ldc.i4.1
0x52322  ldc.i4   0x2649
0x52327  stloc.3
0x52328  ldloca.s 3
0x5232a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5232f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x52334  callvirt instance string [mscorlib]System.Object::ToString()
0x52339  stelem.ref
0x5233a  dup
0x5233b  ldc.i4.2
0x5233c  ldstr    asc_15BF70// ",'"
0x52341  stelem.ref
0x52342  dup
0x52343  ldc.i4.3
0x52344  ldloc.1
0x52345  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x5234a  box      [mscorlib]System.Guid
0x5234f  stelem.ref
0x52350  dup
0x52351  ldc.i4.4
0x52352  ldstr    asc_14EC6A// "','"
0x52357  stelem.ref
0x52358  dup
0x52359  ldc.i4.5
0x5235a  ldc.i4   0x2704
0x5235f  stloc.3
0x52360  ldloca.s 3
0x52362  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52367  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5236c  stelem.ref
0x5236d  dup
0x5236e  ldc.i4.6
0x5236f  ldstr    asc_1235BC// "')"
0x52374  stelem.ref
0x52375  call     string [mscorlib]System.String::Concat(object[])
0x5237a  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x5237f  ldc.i4.1
0x52380  newarr   [mscorlib]System.Char
0x52385  dup
0x52386  ldc.i4.0
0x52387  ldc.i4.s 0x2F
0x52389  stelem.i2
0x5238a  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x5238f  ldstr    aImgsSolutionAd// "/_imgs/solution/addrequiredcomponents.g"...
0x52394  call     string [mscorlib]System.String::Concat(string, string)
0x52399  ldarg.0
0x5239a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5239f  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0x523a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x523a9  ldstr    aBtnaddsubcompo// "btnAddSubcomponents"
0x523ae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x523b3  pop
0x523b4  br       loc_52446
0x523b9  ldloc.0
0x523ba  ldc.i4   0x2649
0x523bf  bne.un   loc_52446
0x523c4  ldarg.2
0x523c5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x523ca  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x523cf  ldarg.2
0x523d0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x523d5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x523da  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x523df  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x523e4  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x523e9  dup
0x523ea  ldarg.0
0x523eb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x523f0  ldstr    aMenuitemLabelA_0// "MenuItem_Label_AddSubcomponents"
0x523f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x523fa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x523ff  dup
0x52400  ldstr    aMscrmSolutionc_3// "Mscrm.SolutionComponentList.callPerform"...
0x52405  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x5240a  dup
0x5240b  ldstr    aImgsSolutionAd// "/_imgs/solution/addrequiredcomponents.g"...
0x52410  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x52415  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5241a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x5241f  dup
0x52420  ldarg.0
0x52421  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
  ... truncated ...
```
