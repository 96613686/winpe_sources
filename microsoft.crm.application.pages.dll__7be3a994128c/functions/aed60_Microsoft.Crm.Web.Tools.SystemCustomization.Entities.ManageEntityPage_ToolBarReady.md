# Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::ToolBarReady

- ea: `0xaed60`
- end: `0xaf26f`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::ToolBarReady`
- size: `1295`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0xaea60`
- `0xaed40`
- `0xaed60`
- `0xb08e0`

## string_xrefs

- `0xaf0c8`: `/_imgs/ico_16_delete.gif`
- `0xaf1c2`: `MenuItem_Label_AddSubcomponents`
- `0xaf25e`: `MenuItem_Label_AddSubcomponents`
- `0xaf1d4`: `Mscrm.SolutionComponentList.manageSelectedEntitySubComponents(`
- `0xaf24e`: `/_imgs/solution/addrequiredcomponents.gif`
- `0xaef2c`: `isrenameable`
- `0xaf010`: `EntityUtil.Actions.UpdateIcons`
- `0xaf045`: `EntityUtil.Actions.UpdateIcons`
- `0xaf01b`: `updateEntityIconsAction();`
- `0xaf03a`: `/_imgs/updateicons_16.png`
- `0xaf09e`: `EntityUtil.Actions.Delete`
- `0xaf0d3`: `EntityUtil.Actions.Delete`
- `0xaf0a9`: `deleteEntityAction();`

## pseudocode

```c

```

## disassembly

```asm
0xaed60  ldarg.0
0xaed61  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xaed66  brfalse.s loc_AED74
0xaed68  ldarg.0
0xaed69  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xaed6e  ldc.i4.1
0xaed6f  bne.un   loc_AEE22
0xaed74  ldarg.2
0xaed75  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaed7a  ldsfld   string [mscorlib]System.String::Empty
0xaed7f  ldarg.0
0xaed80  ldstr    aSaveentityacti// "saveEntityAction(false);"
0xaed85  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetActionName(string action)
0xaed8a  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaed8f  ldc.i4.1
0xaed90  newarr   [mscorlib]System.Char
0xaed95  dup
0xaed96  ldc.i4.0
0xaed97  ldc.i4.s 0x2F
0xaed99  stelem.i2
0xaed9a  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaed9f  ldstr    aImgsIco16SaveG// "/_imgs/ico/16_save.gif"
0xaeda4  call     string [mscorlib]System.String::Concat(string, string)
0xaeda9  ldarg.0
0xaedaa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaedaf  ldstr    aMenuitemLabelS_1// "MenuItem_Label_Save"
0xaedb4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaedb9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0xaedbe  pop
0xaedbf  ldarg.0
0xaedc0  call     instance bool Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::IsInlineMode()
0xaedc5  brtrue   loc_AEE80
0xaedca  ldarg.2
0xaedcb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaedd0  ldarg.0
0xaedd1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaedd6  ldstr    aMenuitemLabelS_0// "MenuItem_Label_SaveClose"
0xaeddb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaede0  ldarg.0
0xaede1  ldstr    aSaveentityacti_0// "saveEntityAction(true);"
0xaede6  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetActionName(string action)
0xaedeb  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaedf0  ldc.i4.1
0xaedf1  newarr   [mscorlib]System.Char
0xaedf6  dup
0xaedf7  ldc.i4.0
0xaedf8  ldc.i4.s 0x2F
0xaedfa  stelem.i2
0xaedfb  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaee00  ldstr    aImgsIco16Savec// "/_imgs/ico/16_saveclose.gif"
0xaee05  call     string [mscorlib]System.String::Concat(string, string)
0xaee0a  ldarg.0
0xaee0b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaee10  ldstr    aMenuitemLabelS_0// "MenuItem_Label_SaveClose"
0xaee15  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaee1a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0xaee1f  pop
0xaee20  br.s     loc_AEE80
0xaee22  ldarg.0
0xaee23  call     instance bool Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::IsInlineMode()
0xaee28  brtrue.s loc_AEE80
0xaee2a  ldarg.2
0xaee2b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaee30  ldarg.0
0xaee31  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaee36  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0xaee3b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaee40  ldarg.0
0xaee41  ldstr    aClosewindow// "closeWindow();"
0xaee46  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetActionName(string action)
0xaee4b  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaee50  ldc.i4.1
0xaee51  newarr   [mscorlib]System.Char
0xaee56  dup
0xaee57  ldc.i4.0
0xaee58  ldc.i4.s 0x2F
0xaee5a  stelem.i2
0xaee5b  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaee60  ldstr    aImgsIco16Close// "/_imgs/ico/16_close.gif"
0xaee65  call     string [mscorlib]System.String::Concat(string, string)
0xaee6a  ldarg.0
0xaee6b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaee70  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0xaee75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaee7a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0xaee7f  pop
0xaee80  ldarg.0
0xaee81  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xaee86  ldc.i4.1
0xaee87  beq.s    loc_AEEAC
0xaee89  ldarg.0
0xaee8a  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xaee8f  ldc.i4.2
0xaee90  bne.un.s loc_AEF0D
0xaee92  ldarg.0
0xaee93  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xaee98  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::IsManaged()
0xaee9d  brtrue.s loc_AEF0D
0xaee9f  ldarg.0
0xaeea0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xaeea5  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_IsParent()
0xaeeaa  brtrue.s loc_AEF0D
0xaeeac  ldarg.2
0xaeead  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaeeb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xaeeb7  ldarg.2
0xaeeb8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaeebd  ldarg.0
0xaeebe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaeec3  ldstr    aMenuitemLabelS_2// "MenuItem_Label_ShowDependency"
0xaeec8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaeecd  ldarg.0
0xaeece  ldstr    aShowdependency_1// "showDependencyAction();"
0xaeed3  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetActionName(string action)
0xaeed8  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaeedd  ldc.i4.1
0xaeede  newarr   [mscorlib]System.Char
0xaeee3  dup
0xaeee4  ldc.i4.0
0xaeee5  ldc.i4.s 0x2F
0xaeee7  stelem.i2
0xaeee8  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaeeed  ldstr    aImgsSolutionSh// "/_imgs/solution/show_dependency.png"
0xaeef2  call     string [mscorlib]System.String::Concat(string, string)
0xaeef7  ldarg.0
0xaeef8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaeefd  ldstr    aMenuitemLabelS_2// "MenuItem_Label_ShowDependency"
0xaef02  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaef07  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0xaef0c  pop
0xaef0d  ldarg.0
0xaef0e  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xaef13  ldc.i4.1
0xaef14  bne.un   loc_AEFC7
0xaef19  ldarg.0
0xaef1a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_entityMD
0xaef1f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0xaef24  brtrue.s loc_AEF5A
0xaef26  ldarg.0
0xaef27  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_entityMD
0xaef2c  ldstr    aIsrenameable// "isrenameable"
0xaef31  ldarg.0
0xaef32  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_entityMD
0xaef37  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsRenameable()
0xaef3c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ManagedPropertyCheckUtil::IsPropertyDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, string, bool)
0xaef41  brfalse.s loc_AEF5A
0xaef43  ldarg.0
0xaef44  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_entityMD
0xaef49  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xaef4e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0xaef53  ldc.i4   0x1068
0xaef58  bne.un.s loc_AEFC7
0xaef5a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaef5f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishCustomizationsPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaef64  brfalse.s loc_AEFC7
0xaef66  ldarg.2
0xaef67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaef6c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xaef71  ldarg.2
0xaef72  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaef77  ldarg.0
0xaef78  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaef7d  ldstr    aSystemcustomiz_426// "SystemCustomization.EntityUtil.Actions."...
0xaef82  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaef87  ldarg.0
0xaef88  ldstr    aPublishentitya// "publishEntityAction();"
0xaef8d  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetActionName(string action)
0xaef92  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaef97  ldc.i4.1
0xaef98  newarr   [mscorlib]System.Char
0xaef9d  dup
0xaef9e  ldc.i4.0
0xaef9f  ldc.i4.s 0x2F
0xaefa1  stelem.i2
0xaefa2  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaefa7  ldstr    aImgsSolutionPu// "/_imgs/solution/publish.png"
0xaefac  call     string [mscorlib]System.String::Concat(string, string)
0xaefb1  ldarg.0
0xaefb2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaefb7  ldstr    aSystemcustomiz_426// "SystemCustomization.EntityUtil.Actions."...
0xaefbc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaefc1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0xaefc6  pop
0xaefc7  ldarg.0
0xaefc8  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xaefcd  ldc.i4.1
0xaefce  bne.un   loc_AF055
0xaefd3  ldarg.0
0xaefd4  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_entityMD
0xaefd9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0xaefde  brfalse.s loc_AF055
0xaefe0  ldarg.0
0xaefe1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_entityMD
0xaefe6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0xaefeb  brfalse.s loc_AF055
0xaefed  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteEntity()
0xaeff2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaeff7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaeffc  brfalse.s loc_AF055
0xaeffe  ldarg.2
0xaefff  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaf004  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xaf009  ldarg.2
0xaf00a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaf00f  ldarg.0
0xaf010  ldstr    aEntityutilActi// "EntityUtil.Actions.UpdateIcons"
0xaf015  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xaf01a  ldarg.0
0xaf01b  ldstr    aUpdateentityic// "updateEntityIconsAction();"
0xaf020  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetActionName(string action)
0xaf025  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaf02a  ldc.i4.1
0xaf02b  newarr   [mscorlib]System.Char
0xaf030  dup
0xaf031  ldc.i4.0
0xaf032  ldc.i4.s 0x2F
0xaf034  stelem.i2
0xaf035  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaf03a  ldstr    aImgsUpdateicon// "/_imgs/updateicons_16.png"
0xaf03f  call     string [mscorlib]System.String::Concat(string, string)
0xaf044  ldarg.0
0xaf045  ldstr    aEntityutilActi// "EntityUtil.Actions.UpdateIcons"
0xaf04a  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xaf04f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0xaf054  pop
0xaf055  ldarg.0
0xaf056  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xaf05b  ldc.i4.1
0xaf05c  bne.un   loc_AF0E3
0xaf061  ldarg.0
0xaf062  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_entityMD
0xaf067  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0xaf06c  brfalse.s loc_AF0E3
0xaf06e  ldarg.0
0xaf06f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_entityMD
0xaf074  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0xaf079  brfalse.s loc_AF0E3
0xaf07b  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteEntity()
0xaf080  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaf085  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaf08a  brfalse.s loc_AF0E3
0xaf08c  ldarg.2
0xaf08d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaf092  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xaf097  ldarg.2
0xaf098  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaf09d  ldarg.0
0xaf09e  ldstr    aEntityutilActi_0// "EntityUtil.Actions.Delete"
0xaf0a3  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xaf0a8  ldarg.0
0xaf0a9  ldstr    aDeleteentityac// "deleteEntityAction();"
0xaf0ae  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetActionName(string action)
0xaf0b3  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaf0b8  ldc.i4.1
0xaf0b9  newarr   [mscorlib]System.Char
0xaf0be  dup
0xaf0bf  ldc.i4.0
0xaf0c0  ldc.i4.s 0x2F
0xaf0c2  stelem.i2
0xaf0c3  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaf0c8  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0xaf0cd  call     string [mscorlib]System.String::Concat(string, string)
0xaf0d2  ldarg.0
0xaf0d3  ldstr    aEntityutilActi_0// "EntityUtil.Actions.Delete"
0xaf0d8  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xaf0dd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0xaf0e2  pop
0xaf0e3  ldarg.0
0xaf0e4  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xaf0e9  ldc.i4.1
0xaf0ea  beq.s    loc_AF10F
0xaf0ec  ldarg.0
0xaf0ed  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xaf0f2  ldc.i4.2
0xaf0f3  bne.un.s loc_AF170
0xaf0f5  ldarg.0
0xaf0f6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xaf0fb  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::IsManaged()
0xaf100  brtrue.s loc_AF170
0xaf102  ldarg.0
0xaf103  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0xaf108  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_IsParent()
0xaf10d  brtrue.s loc_AF170
0xaf10f  ldarg.2
0xaf110  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaf115  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xaf11a  ldarg.2
0xaf11b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xaf120  ldarg.0
0xaf121  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaf126  ldstr    aMenuitemLabelM// "MenuItem_Label_ManagedProperties"
0xaf12b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaf130  ldarg.0
0xaf131  ldstr    aManagedpropert_2// "managedPropertyAction();"
0xaf136  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetActionName(string action)
0xaf13b  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaf140  ldc.i4.1
0xaf141  newarr   [mscorlib]System.Char
0xaf146  dup
0xaf147  ldc.i4.0
  ... truncated ...
```
