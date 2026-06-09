# Microsoft.Crm.Application.Controls.AppViewSelector::ConfigureHeader

- ea: `0x911c0`
- end: `0x915e3`
- name: `Microsoft.Crm.Application.Controls.AppViewSelector::ConfigureHeader`
- size: `1059`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa6b0`
- `0xa760`
- `0xa780`
- `0xa7c0`
- `0xa870`
- `0xa8a0`
- `0xa8d0`
- `0xa950`
- `0xa970`
- `0x90b20`
- `0x90b70`
- `0x90ba0`
- `0x90c70`
- `0x90c90`
- `0x90cf0`
- `0x90e70`
- `0x90ee0`
- `0x90fb0`
- `0x911c0`
- `0x91620`

## string_xrefs

- `0x911dc`: `/_static/_common/scripts/stage.js`
- `0x913ac`: `createPersonalViewEnabled`
- `0x913e4`: `systemViewsXml`
- `0x913fa`: `userViewsXml`
- `0x91483`: `selectOptionsXml`
- `0x91499`: `createPersonalViewLabel`
- `0x914a3`: `CRM_Create_Personal_View`

## pseudocode

```c

```

## disassembly

```asm
0x911c0  ldarg.0
0x911c1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x911c6  ldarg.0
0x911c7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x911cc  ldc.i4   0x200
0x911d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0x911d6  ldarg.0
0x911d7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x911dc  ldstr    aStaticCommonSc// "/_static/_common/scripts/stage.js"
0x911e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x911e6  ldarg.0
0x911e7  ldarg.0
0x911e8  ldfld    bool Microsoft.Crm.Application.Controls.AppViewSelector::_isWebClientVisualRefreshEnabled
0x911ed  brtrue.s loc_911F6
0x911ef  ldstr    aMsCrmImagestri_0// "ms-crm-ImageStrip-pinned_16"
0x911f4  br.s     loc_911FB
0x911f6  ldstr    aMsCrmImagestri_1// "ms-crm-ImageStrip-pinned_visualrefresh"
0x911fb  stfld    string Microsoft.Crm.Application.Controls.AppViewSelector::ViewSelectorPinClassName
0x91200  ldarg.0
0x91201  ldarg.0
0x91202  ldfld    bool Microsoft.Crm.Application.Controls.AppViewSelector::_isWebClientVisualRefreshEnabled
0x91207  brtrue.s loc_91210
0x91209  ldstr    aMsCrmImagestri_2// "ms-crm-ImageStrip-pin_16"
0x9120e  br.s     loc_91215
0x91210  ldstr    aMsCrmImagestri_3// "ms-crm-ImageStrip-pin_visualrefresh"
0x91215  stfld    string Microsoft.Crm.Application.Controls.AppViewSelector::ViewSelectorUnPinClassName
0x9121a  ldarg.0
0x9121b  ldarg.0
0x9121c  ldfld    bool Microsoft.Crm.Application.Controls.AppViewSelector::_isWebClientVisualRefreshEnabled
0x91221  brtrue.s loc_9122A
0x91223  ldstr    aMsCrmImagestri_4// "ms-crm-ImageStrip-pinned_16_RTL"
0x91228  br.s     loc_9122F
0x9122a  ldstr    aMsCrmImagestri_5// "ms-crm-ImageStrip-pinned_visualrefresh_"...
0x9122f  stfld    string Microsoft.Crm.Application.Controls.AppViewSelector::ViewSelectorPinRtlClassName
0x91234  ldarg.0
0x91235  ldarg.0
0x91236  ldfld    bool Microsoft.Crm.Application.Controls.AppViewSelector::_isWebClientVisualRefreshEnabled
0x9123b  brtrue.s loc_91244
0x9123d  ldstr    aMsCrmImagestri_6// "ms-crm-ImageStrip-pin_16_RTL"
0x91242  br.s     loc_91249
0x91244  ldstr    aMsCrmImagestri_7// "ms-crm-ImageStrip-pin_visualrefresh_RTL"
0x91249  stfld    string Microsoft.Crm.Application.Controls.AppViewSelector::ViewSelectorUnPinRtlClassName
0x9124e  ldarg.0
0x9124f  ldarg.0
0x91250  ldfld    bool Microsoft.Crm.Application.Controls.AppViewSelector::_isWebClientVisualRefreshEnabled
0x91255  brtrue.s loc_9125E
0x91257  ldstr    aImgsGridPinned// "/_imgs/grid/pinned_16.png"
0x9125c  br.s     loc_91263
0x9125e  ldstr    aImgsGridPinned_0// "/_imgs/grid/pinned_visualrefresh.png"
0x91263  stfld    string Microsoft.Crm.Application.Controls.AppViewSelector::ViewSelectorPinnedIconPath
0x91268  ldarg.0
0x91269  ldarg.0
0x9126a  ldfld    bool Microsoft.Crm.Application.Controls.AppViewSelector::_isWebClientVisualRefreshEnabled
0x9126f  brtrue.s loc_91278
0x91271  ldstr    aImgsGridPin16P// "/_imgs/grid/pin_16.png"
0x91276  br.s     loc_9127D
0x91278  ldstr    aImgsGridPinVis// "/_imgs/grid/pin_visualrefresh.png"
0x9127d  stfld    string Microsoft.Crm.Application.Controls.AppViewSelector::ViewSelectorUnPinIconPath
0x91282  ldarg.0
0x91283  ldarg.0
0x91284  ldfld    bool Microsoft.Crm.Application.Controls.AppViewSelector::_isWebClientVisualRefreshEnabled
0x91289  brtrue.s loc_91292
0x9128b  ldstr    aImgsGridPinned_1// "/_imgs/grid/pinned_16_rtl.png"
0x91290  br.s     loc_91297
0x91292  ldstr    aImgsGridPinned_2// "/_imgs/grid/pinned_visualrefresh_rtl.pn"...
0x91297  stfld    string Microsoft.Crm.Application.Controls.AppViewSelector::ViewSelectorPinnedRtlIconPath
0x9129c  ldarg.0
0x9129d  ldarg.0
0x9129e  ldfld    bool Microsoft.Crm.Application.Controls.AppViewSelector::_isWebClientVisualRefreshEnabled
0x912a3  brtrue.s loc_912AC
0x912a5  ldstr    aImgsGridPinHov// "/_imgs/grid/pin_hover_16_rtl.png"
0x912aa  br.s     loc_912B1
0x912ac  ldstr    aImgsGridPinVis_0// "/_imgs/grid/pin_visualrefresh_hover_rtl"...
0x912b1  stfld    string Microsoft.Crm.Application.Controls.AppViewSelector::ViewSelectorUnPinRtlIconPath
0x912b6  ldarg.0
0x912b7  call     instance void Microsoft.Crm.Application.Controls.AppViewSelector::Initialize()
0x912bc  ldarg.0
0x912bd  ldfld    class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppViewSelector::_viewSelector
0x912c2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x912c7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x912cc  stloc.0
0x912cd  ldarg.0
0x912ce  call     instance bool Microsoft.Crm.Application.Controls.AppViewSelector::get_ShowNewVSControl()
0x912d3  brfalse  loc_9151E
0x912d8  ldloc.0
0x912d9  ldstr    aShownewvscontr// "showNewVSControl"
0x912de  ldarg.0
0x912df  call     instance bool Microsoft.Crm.Application.Controls.AppViewSelector::get_ShowNewVSControl()
0x912e4  box      [mscorlib]System.Boolean
0x912e9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x912ee  ldloc.0
0x912ef  ldstr    aShoworiginalse// "showOriginalSelectBox"
0x912f4  ldarg.0
0x912f5  call     instance bool Microsoft.Crm.Application.Controls.AppViewSelector::get_ShowOriginalSelectBox()
0x912fa  box      [mscorlib]System.Boolean
0x912ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91304  ldloc.0
0x91305  ldstr    aViewentityname// "viewEntityName"
0x9130a  ldarg.0
0x9130b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.AppViewSelector::get_ReturnedEntityType()
0x91310  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x91315  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9131a  ldloc.0
0x9131b  ldstr    aSelectedsavedq// "selectedSavedQuery"
0x91320  ldarg.0
0x91321  ldfld    class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppViewSelector::_viewSelector
0x91326  callvirt instance string Microsoft.Crm.Controls.ViewSelector::get_SelectedSavedQuery()
0x9132b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91330  ldloc.0
0x91331  ldstr    aSelectedsavedq_0// "selectedSavedQueryName"
0x91336  ldarg.0
0x91337  ldfld    class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppViewSelector::_viewSelector
0x9133c  callvirt instance string Microsoft.Crm.Controls.ViewSelector::get_SelectedSavedQueryName()
0x91341  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91346  ldloc.0
0x91347  ldstr    aSelectedsavedq_1// "selectedSavedQueryType"
0x9134c  ldarg.0
0x9134d  ldfld    class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppViewSelector::_viewSelector
0x91352  callvirt instance int32 Microsoft.Crm.Controls.ViewSelector::get_SelectedSavedQueryType()
0x91357  stloc.1
0x91358  ldloca.s 1
0x9135a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9135f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x91364  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91369  ldloc.0
0x9136a  ldstr    aUserselectedde// "userSelectedDefaultView"
0x9136f  ldarg.0
0x91370  ldfld    class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppViewSelector::_viewSelector
0x91375  callvirt instance string Microsoft.Crm.Controls.ViewSelector::get_IsUserSelectedDefaultView()
0x9137a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9137f  ldloc.0
0x91380  ldstr    aUserownedview// "userOwnedView"
0x91385  ldarg.0
0x91386  ldfld    class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppViewSelector::_viewSelector
0x9138b  callvirt instance string Microsoft.Crm.Controls.ViewSelector::get_IsUserOwnedView()
0x91390  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91395  ldloc.0
0x91396  ldstr    aQuickfindquery// "quickFindQuery"
0x9139b  ldarg.0
0x9139c  ldfld    class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppViewSelector::_viewSelector
0x913a1  callvirt instance string Microsoft.Crm.Controls.ViewSelector::get_QuickFindQuery()
0x913a6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x913ab  ldloc.0
0x913ac  ldstr    aCreatepersonal// "createPersonalViewEnabled"
0x913b1  ldarg.0
0x913b2  call     instance bool Microsoft.Crm.Application.Controls.AppViewSelector::get_DisplayCreatePersonalView()
0x913b7  brfalse.s loc_913D8
0x913b9  ldarg.0
0x913ba  call     instance bool Microsoft.Crm.Application.Controls.AppViewSelector::get_IsValidForAdvancedFind()
0x913bf  brfalse.s loc_913D8
0x913c1  ldarg.0
0x913c2  call     instance bool Microsoft.Crm.Application.Controls.AppViewSelector::get_HasCreateAccessOnSavedViews()
0x913c7  brfalse.s loc_913D8
0x913c9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x913ce  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x913d3  ldc.i4.0
0x913d4  ceq
0x913d6  br.s     loc_913D9
0x913d8  ldc.i4.0
0x913d9  box      [mscorlib]System.Boolean
0x913de  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x913e3  ldloc.0
0x913e4  ldstr    aSystemviewsxml// "systemViewsXml"
0x913e9  ldarg.0
0x913ea  ldfld    class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppViewSelector::_viewSelector
0x913ef  callvirt instance string Microsoft.Crm.Controls.ViewSelector::get_SystemViewsXml()
0x913f4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x913f9  ldloc.0
0x913fa  ldstr    aUserviewsxml// "userViewsXml"
0x913ff  ldarg.0
0x91400  ldfld    class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppViewSelector::_viewSelector
0x91405  callvirt instance string Microsoft.Crm.Controls.ViewSelector::get_UserViewsXml()
0x9140a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9140f  ldloc.0
0x91410  ldstr    aSystemviewslab// "systemViewsLabel"
0x91415  ldarg.0
0x91416  ldfld    string Microsoft.Crm.Application.Controls.AppViewSelector::_systemGroupName
0x9141b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91420  ldloc.0
0x91421  ldstr    aUserviewslabel// "userViewsLabel"
0x91426  ldarg.0
0x91427  ldfld    string Microsoft.Crm.Application.Controls.AppViewSelector::_userGroupName
0x9142c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91431  ldloc.0
0x91432  ldstr    aCustomviewslab// "customViewsLabel"
0x91437  ldarg.0
0x91438  ldfld    string Microsoft.Crm.Application.Controls.AppViewSelector::_customGroupName
0x9143d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91442  ldloc.0
0x91443  ldstr    aRenderforprint// "renderForPrint"
0x91448  ldarg.0
0x91449  call     instance valuetype Microsoft.Crm.Application.Forms.FormControlRenderMode Microsoft.Crm.Application.Controls.AppViewSelector::get_RenderMode()
0x9144e  ldc.i4.0
0x9144f  ceq
0x91451  box      [mscorlib]System.Boolean
0x91456  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9145b  ldloc.0
0x9145c  ldstr    aIsactivitiesvi// "isActivitiesViewSelector"
0x91461  ldarg.0
0x91462  ldfld    bool Microsoft.Crm.Application.Controls.AppViewSelector::_isActivitiesViewSelector
0x91467  box      [mscorlib]System.Boolean
0x9146c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91471  ldloc.0
0x91472  ldstr    aActivitylist// "activityList"
0x91477  ldarg.0
0x91478  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EntityReference[] Microsoft.Crm.Application.Controls.AppViewSelector::getActivities()
0x9147d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91482  ldloc.0
0x91483  ldstr    aSelectoptionsx// "selectOptionsXml"
0x91488  ldarg.0
0x91489  ldfld    class Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Application.Controls.AppViewSelector::_viewSelector
0x9148e  callvirt instance string Microsoft.Crm.Controls.ViewSelector::get_SelectOptionsXml()
0x91493  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91498  ldloc.0
0x91499  ldstr    aCreatepersonal_0// "createPersonalViewLabel"
0x9149e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x914a3  ldstr    aCrmCreatePerso// "CRM_Create_Personal_View"
0x914a8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x914ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x914b2  ldloc.0
0x914b3  ldstr    aSavefiltersasn// "saveFiltersAsNewViewLabel"
0x914b8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x914bd  ldstr    aCrmSaveAsNewVi// "CRM_Save_As_New_View"
0x914c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x914c7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x914cc  ldloc.0
0x914cd  ldstr    aSavefilterstoc_0// "saveFiltersToCurrentViewLabel"
0x914d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x914d7  ldstr    aCrmSaveToCurre// "CRM_Save_To_Current_View"
0x914dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x914e1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x914e6  ldloc.0
0x914e7  ldstr    aOndefaultviewt// "onDefaultViewToolTip"
0x914ec  ldarg.0
0x914ed  ldfld    string Microsoft.Crm.Application.Controls.AppViewSelector::_onDefaultViewToolTip
0x914f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x914f7  ldloc.0
0x914f8  ldstr    aSetdefaultview// "setDefaultViewToolTip"
0x914fd  ldarg.0
0x914fe  ldfld    string Microsoft.Crm.Application.Controls.AppViewSelector::_setDefaultViewToolTip
0x91503  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x91508  ldloc.0
0x91509  ldstr    aGridfiltersena// "gridFiltersEnabled"
0x9150e  ldarg.0
0x9150f  call     instance bool Microsoft.Crm.Application.Controls.AppViewSelector::get_IsValidForAdvancedFind()
0x91514  box      [mscorlib]System.Boolean
0x91519  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9151e  ldarg.0
0x9151f  call     instance valuetype Microsoft.Crm.Application.Forms.FormControlRenderMode Microsoft.Crm.Application.Controls.AppViewSelector::get_RenderMode()
0x91524  brfalse  loc_915E2
0x91529  ldarg.0
0x9152a  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x9152f  brtrue   loc_915E2
0x91534  ldarg.0
0x91535  ldstr    aMscrmGridviews// "Mscrm.GridViewSelector"
0x9153a  ldloc.0
0x9153b  ldnull
0x9153c  ldnull
0x9153d  ldarg.0
0x9153e  call     instance string Microsoft.Crm.Application.Controls.AppViewSelector::get_RenderId()
0x91543  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x91548  ldarg.0
0x91549  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9154e  ldstr    aStaticGridGrid// "/_static/_grid/GridControl.js"
0x91553  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x91558  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9155d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x91562  ldarg.0
0x91563  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x91568  brfalse.s loc_915E2
0x9156a  ldarg.0
0x9156b  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x91570  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x91575  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9157a  ldstr    aIsturboform// "isTurboForm"
0x9157f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x91584  brfalse.s loc_915E2
0x91586  ldarg.0
0x91587  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9158c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x91591  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x91596  ldstr    aIsturboform// "isTurboForm"
0x9159b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x915a0  call     bool [mscorlib]System.Boolean::Parse(string)
0x915a5  brfalse.s loc_915E2
0x915a7  ldarg.0
0x915a8  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x915ad  ldstr    aMscrmGridviews// "Mscrm.GridViewSelector"
0x915b2  ldloc.0
0x915b3  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::ConvertDictionaryToJson(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x915b8  ldnull
0x915b9  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::ConvertDictionaryToJSObject(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x915be  ldnull
0x915bf  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::ConvertDictionaryToJSObject(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x915c4  ldarg.0
0x915c5  call     instance string Microsoft.Crm.Application.Controls.AppViewSelector::get_RenderId()
0x915ca  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::GetClientAjaxComponentScript(string, string, string, string, string)
0x915cf  stloc.2
0x915d0  ldarg.0
0x915d1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
  ... truncated ...
```
