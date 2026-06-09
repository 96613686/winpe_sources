# Microsoft.Crm.Application.Controls.AppNavBar::ConfigureHeader

- ea: `0x8c1c0`
- end: `0x8c5e9`
- name: `Microsoft.Crm.Application.Controls.AppNavBar::ConfigureHeader`
- size: `1065`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8c1c0`
- `0x8c640`

## string_xrefs

- `0x8c521`: `MenuItem_Label_Copy_Shortcut`
- `0x8c4e3`: `openActionTitle`
- `0x8c4ed`: `Grid_RenderContextMenu_Label_Open`
- `0x8c4fd`: `openInNewWindowActionTitle`
- `0x8c507`: `Grid_RenderContextMenu_Label_OpenInNewWindow`
- `0x8c517`: `copyShortcutActionTitle`
- `0x8c563`: `areasXslXml`
- `0x8c575`: `subAreasXslXml`
- `0x8c5c3`: `siteMapXml`

## pseudocode

```c

```

## disassembly

```asm
0x8c1c0  ldc.i4.0
0x8c1c1  stloc.0
0x8c1c2  ldarg.0
0x8c1c3  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x8c1c8  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8c1cd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8c1d2  ldstr    aWeb// "web"
0x8c1d7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8c1dc  brfalse.s loc_8C20C
0x8c1de  ldarg.0
0x8c1df  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x8c1e4  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8c1e9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8c1ee  ldstr    aWeb// "web"
0x8c1f3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8c1f8  callvirt instance string [mscorlib]System.Object::ToString()
0x8c1fd  ldloca.s 8
0x8c1ff  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x8c204  brfalse.s loc_8C20C
0x8c206  ldloc.s  8
0x8c208  brtrue.s loc_8C20C
0x8c20a  ldc.i4.1
0x8c20b  stloc.0
0x8c20c  ldloc.0
0x8c20d  brfalse.s loc_8C210
0x8c20f  ret
0x8c210  ldarg.0
0x8c211  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x8c216  ldarg.0
0x8c217  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8c21c  ldstr    aAppnavAppnavba// "/appnav/appnavbar.css.aspx"
0x8c221  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8c226  ldarg.0
0x8c227  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x8c22c  ldstr    aStaticControls_17// "/_static/_controls/AppNav/CrmNavBar.js"
0x8c231  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8c236  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x8c23b  stloc.1
0x8c23c  ldarg.0
0x8c23d  ldfld    string Microsoft.Crm.Application.Controls.AppNavBar::_selectedAreaId
0x8c242  stloc.2
0x8c243  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x8c248  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x8c24d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8c252  ldstr    aAreaid// "areaId"
0x8c257  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8c25c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8c261  brtrue.s loc_8C27D
0x8c263  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x8c268  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x8c26d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8c272  ldstr    aAreaid// "areaId"
0x8c277  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8c27c  stloc.2
0x8c27d  ldloc.1
0x8c27e  ldstr    aSelectedareaid// "selectedAreaId"
0x8c283  ldloc.2
0x8c284  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c289  ldarg.0
0x8c28a  ldfld    string Microsoft.Crm.Application.Controls.AppNavBar::_selectedSubAreaId
0x8c28f  stloc.3
0x8c290  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x8c295  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x8c29a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8c29f  ldstr    aSubareaid// "subareaId"
0x8c2a4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8c2a9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8c2ae  brtrue.s loc_8C2CA
0x8c2b0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x8c2b5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x8c2ba  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8c2bf  ldstr    aSubareaid// "subareaId"
0x8c2c4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8c2c9  stloc.3
0x8c2ca  ldloc.1
0x8c2cb  ldstr    aSelectedsubare// "selectedSubAreaId"
0x8c2d0  ldloc.3
0x8c2d1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c2d6  ldloc.1
0x8c2d7  ldstr    aEmptytitle// "emptyTitle"
0x8c2dc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c2e1  ldstr    aDatamanagement// "DataManagement.ImportMap.PicklistMap.Em"...
0x8c2e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c2eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c2f0  ldloc.1
0x8c2f1  ldstr    aDefaultareaid// "defaultAreaId"
0x8c2f6  ldarg.0
0x8c2f7  ldfld    string Microsoft.Crm.Application.Controls.AppNavBar::_selectedAreaId
0x8c2fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c301  ldloc.1
0x8c302  ldstr    aDefaultsubarea// "defaultSubAreaId"
0x8c307  ldarg.0
0x8c308  ldfld    string Microsoft.Crm.Application.Controls.AppNavBar::_selectedSubAreaId
0x8c30d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c312  ldloc.1
0x8c313  ldstr    aAltgroupexpand// "altGroupExpanded"
0x8c318  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c31d  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0x8c322  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c327  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c32c  ldloc.1
0x8c32d  ldstr    aAltgroupcollap// "altGroupCollapsed"
0x8c332  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c337  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0x8c33c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c341  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c346  ldloc.1
0x8c347  ldstr    aCollapsednavla// "collapsedNavLabel"
0x8c34c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c351  ldstr    aNavbarCollapse// "NavBar_Collapsed_Caption"
0x8c356  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c35b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c360  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c365  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c36a  brtrue.s loc_8C388
0x8c36c  ldloc.1
0x8c36d  ldstr    aActualwidth// "actualWidth"
0x8c372  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c377  ldstr    aCrmAppnavWidth// "CRM_AppNav_Width"
0x8c37c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c381  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c386  br.s     loc_8C3A2
0x8c388  ldloc.1
0x8c389  ldstr    aActualwidth// "actualWidth"
0x8c38e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c393  ldstr    aCrmAppnavWidth_0// "CRM_AppNav_Width_Touch_Experience"
0x8c398  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c39d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c3a2  ldloc.1
0x8c3a3  ldstr    aCollapsedwidth// "collapsedWidth"
0x8c3a8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c3ad  ldstr    aCrmAppnavColla// "CRM_AppNav_Collapsed_Width"
0x8c3b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c3b7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c3bc  ldloc.1
0x8c3bd  ldstr    aTitleformat_0// "titleFormat"
0x8c3c2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c3c7  ldstr    aFormTitleMask// "Form_Title_Mask"
0x8c3cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c3d1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c3d6  ldloc.1
0x8c3d7  ldstr    aAlthomeicon// "altHomeIcon"
0x8c3dc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c3e1  ldstr    aHomeiconToolti// "HomeIcon_Tooltip"
0x8c3e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c3eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c3f0  ldloc.1
0x8c3f1  ldstr    aAltrecentlyvie// "altRecentlyViewedIcon"
0x8c3f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c3fb  ldstr    aRecentlyviewed// "RecentlyViewed_Tooltip"
0x8c400  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c405  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c40a  ldloc.1
0x8c40b  ldstr    aViewselectorto// "viewSelectorTooltip"
0x8c410  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c415  ldstr    aCrmAppnavViews// "CRM_AppNav_ViewSelector_Tooltip"
0x8c41a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c41f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c424  ldloc.1
0x8c425  ldstr    aViewselectoral// "viewSelectorAltText"
0x8c42a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c42f  ldstr    aCrmAppnavViews_0// "CRM_AppNav_ViewSelector_Alt"
0x8c434  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c439  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c43e  ldloc.1
0x8c43f  ldstr    aFlyoutanimatio// "flyoutAnimation"
0x8c444  ldc.i4.1
0x8c445  box      [mscorlib]System.Boolean
0x8c44a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c44f  ldloc.1
0x8c450  ldstr    aNewrecordtitle// "newRecordTitle"
0x8c455  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c45a  ldstr    aButtonLabelNew// "Button_Label_New"
0x8c45f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c464  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c469  ldloc.1
0x8c46a  ldstr    aNewrecordtoolt// "newRecordTooltip"
0x8c46f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c474  ldstr    aTooltipLookupN// "ToolTip_Lookup_New"
0x8c479  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c47e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c483  ldloc.1
0x8c484  ldstr    aNewactivitytit// "newActivityTitle"
0x8c489  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c48e  ldstr    aRibbonJewelNew// "Ribbon.Jewel.NewActivity"
0x8c493  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c498  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c49d  ldloc.1
0x8c49e  ldstr    aNewactivitytoo// "newActivityTooltip"
0x8c4a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c4a8  ldstr    aTooltipNewActi// "ToolTip_New_Activity"
0x8c4ad  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c4b2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c4b7  ldloc.1
0x8c4b8  ldstr    aRecentlyvisite// "recentlyVisitedTitle"
0x8c4bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c4c2  ldstr    aRecentlyviewed_0// "RecentlyViewed_Header_Title"
0x8c4c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c4cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c4d1  ldloc.1
0x8c4d2  ldstr    aActivitylist// "activityList"
0x8c4d7  ldarg.0
0x8c4d8  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EntityReference[] Microsoft.Crm.Application.Controls.AppNavBar::getActivites()
0x8c4dd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c4e2  ldloc.1
0x8c4e3  ldstr    aOpenactiontitl// "openActionTitle"
0x8c4e8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c4ed  ldstr    aGridRendercont// "Grid_RenderContextMenu_Label_Open"
0x8c4f2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c4f7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c4fc  ldloc.1
0x8c4fd  ldstr    aOpeninnewwindo// "openInNewWindowActionTitle"
0x8c502  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c507  ldstr    aGridRendercont_0// "Grid_RenderContextMenu_Label_OpenInNewW"...
0x8c50c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c511  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c516  ldloc.1
0x8c517  ldstr    aCopyshortcutac// "copyShortcutActionTitle"
0x8c51c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c521  ldstr    aMenuitemLabelC_0// "MenuItem_Label_Copy_Shortcut"
0x8c526  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c52b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c530  ldloc.1
0x8c531  ldstr    aSendshortcutac// "sendShortcutActionTitle"
0x8c536  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c53b  ldstr    aMenuitemLabelS_5// "MenuItem_Label_Send_Shortcut"
0x8c540  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c545  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c54a  ldstr    aAreasXsl// "areas.xsl"
0x8c54f  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::LoadXmlDocumentFromFileId(string)
0x8c554  stloc.s  4
0x8c556  ldstr    aSubareasXsl// "subareas.xsl"
0x8c55b  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::LoadXmlDocumentFromFileId(string)
0x8c560  stloc.s  5
0x8c562  ldloc.1
0x8c563  ldstr    aAreasxslxml// "areasXslXml"
0x8c568  ldloc.s  4
0x8c56a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8c56f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c574  ldloc.1
0x8c575  ldstr    aSubareasxslxml// "subAreasXslXml"
0x8c57a  ldloc.s  5
0x8c57c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8c581  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c586  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8c58b  stloc.s  6
0x8c58d  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x8c592  stloc.s  7
0x8c594  ldloc.s  7
0x8c596  ldc.i4.1
0x8c597  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x8c59c  ldloc.s  6
0x8c59e  ldloc.s  7
0x8c5a0  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x8c5a5  stloc.s  9
0x8c5a7  ldarg.0
0x8c5a8  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap Microsoft.Crm.Application.Controls.AppNavBar::_siteMap
0x8c5ad  ldloc.s  9
0x8c5af  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap::Deserialize(class [System.Xml]System.Xml.XmlWriter)
0x8c5b4  leave.s  loc_8C5C2
0x8c5b6  ldloc.s  9
0x8c5b8  brfalse.s loc_8C5C1
0x8c5ba  ldloc.s  9
0x8c5bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c5c1  endfinally
0x8c5c2  ldloc.1
0x8c5c3  ldstr    aSitemapxml// "siteMapXml"
0x8c5c8  ldloc.s  6
0x8c5ca  callvirt instance string [mscorlib]System.Object::ToString()
0x8c5cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8c5d4  ldarg.0
0x8c5d5  ldstr    aMscrmAppnavbar// "Mscrm.AppNavBar"
0x8c5da  ldloc.1
0x8c5db  ldnull
0x8c5dc  ldnull
0x8c5dd  ldarg.0
0x8c5de  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x8c5e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x8c5e8  ret
```
