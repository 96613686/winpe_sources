# Microsoft.Crm.Application.Controls.VisualizationCompositeControl::GetAppGridLite

- ea: `0x61f60`
- end: `0x62275`
- name: `Microsoft.Crm.Application.Controls.VisualizationCompositeControl::GetAppGridLite`
- size: `789`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x617e0`

## callees

- `0x54900`
- `0x55e40`
- `0x55e90`
- `0x55eb0`
- `0x55ec0`
- `0x56060`
- `0x56070`
- `0x58c50`
- `0x61f60`

## string_xrefs

- `0x62150`: `customControlXmlParam`
- `0x62162`: `customControlXmlParam`
- `0x62172`: `customControlXmlParam`
- `0x62239`: `teamTemplateId`
- `0x62249`: `teamTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x61f60  ldarg.0
0x61f61  ldfld    class Microsoft.Crm.Application.Controls.ICustomGridProviderFactory Microsoft.Crm.Application.Controls.VisualizationCompositeControl::_customGridProviderFactory
0x61f66  ldarg.1
0x61f67  newobj   instance void Microsoft.Crm.Application.Controls.AppGridLite::.ctor(class Microsoft.Crm.Application.Controls.ICustomGridProviderFactory customGridProviderFactory, [opt] string maxSelectableItems)
0x61f6c  stloc.0
0x61f6d  ldloc.0
0x61f6e  ldarg.0
0x61f6f  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x61f74  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x61f79  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x61f7e  ldloc.0
0x61f7f  ldc.i4.1
0x61f80  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_IsGridFilteringEnabled(bool)
0x61f85  ldloc.0
0x61f86  ldarg.0
0x61f87  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x61f8c  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType Microsoft.Crm.Application.Controls.AppGrid::get_ViewType()
0x61f91  callvirt instance void Microsoft.Crm.Application.Controls.AppGrid::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType value)
0x61f96  ldloc.0
0x61f97  ldarg.0
0x61f98  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x61f9d  callvirt instance string Microsoft.Crm.Application.Controls.AppGrid::get_ViewId()
0x61fa2  callvirt instance void Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string value)
0x61fa7  ldloc.0
0x61fa8  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::.ctor()
0x61fad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_DataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider)
0x61fb2  ldloc.0
0x61fb3  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataProvider()
0x61fb8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x61fbd  ldstr    aViewid_1// "viewid"
0x61fc2  ldloc.0
0x61fc3  callvirt instance string Microsoft.Crm.Application.Controls.AppGrid::get_ViewId()
0x61fc8  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x61fcd  ldloc.0
0x61fce  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataProvider()
0x61fd3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x61fd8  ldstr    aRenderasync// "RenderAsync"
0x61fdd  ldstr    a1_0// "1"
0x61fe2  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x61fe7  ldloc.0
0x61fe8  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataProvider()
0x61fed  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x61ff2  ldstr    aLoadondemand// "LoadOnDemand"
0x61ff7  ldarg.0
0x61ff8  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x61ffd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62002  ldstr    aLoadondemand// "LoadOnDemand"
0x62007  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6200c  ldstr    a0// "0"
0x62011  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62016  brtrue.s loc_6201F
0x62018  ldstr    a1_0// "1"
0x6201d  br.s     loc_62024
0x6201f  ldstr    a0// "0"
0x62024  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x62029  ldloc.0
0x6202a  ldarg.0
0x6202b  ldfld    class Microsoft.Crm.Application.Controls.ICustomGridProviderFactory Microsoft.Crm.Application.Controls.VisualizationCompositeControl::_customGridProviderFactory
0x62030  newobj   instance void Microsoft.Crm.Application.Controls.GridUIProvider::.ctor(class Microsoft.Crm.Application.Controls.ICustomGridProviderFactory customGridProviderFactory)
0x62035  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_UIProvider(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider)
0x6203a  ldloc.0
0x6203b  ldarg.0
0x6203c  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62041  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Expandable()
0x62046  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_Expandable(bool)
0x6204b  ldloc.0
0x6204c  ldarg.0
0x6204d  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62052  callvirt instance bool Microsoft.Crm.Application.Controls.AppGrid::get_ShowJumpBar()
0x62057  callvirt instance void Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool value)
0x6205c  ldloc.0
0x6205d  ldarg.0
0x6205e  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62063  callvirt instance unsigned int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RecordsPerPage()
0x62068  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_RecordsPerPage(unsigned int32)
0x6206d  ldloc.0
0x6206e  ldarg.0
0x6206f  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62074  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_MaxRowsBeforeScroll()
0x62079  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_MaxRowsBeforeScroll(int32)
0x6207e  ldloc.0
0x6207f  ldarg.0
0x62080  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62085  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TabIndex()
0x6208a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_TabIndex(int32)
0x6208f  ldloc.0
0x62090  ldc.i4.1
0x62091  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_RefreshAsynchronous(bool)
0x62096  ldloc.0
0x62097  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x6209c  ldstr    aSubgridautoexp// "subgridAutoExpand"
0x620a1  ldarg.0
0x620a2  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x620a7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x620ac  ldstr    aSubgridautoexp// "subgridAutoExpand"
0x620b1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x620b6  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x620bb  ldloc.0
0x620bc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x620c1  ldstr    aRelname// "relName"
0x620c6  ldarg.0
0x620c7  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x620cc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x620d1  ldstr    aRelname// "relName"
0x620d6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x620db  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x620e0  ldloc.0
0x620e1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x620e6  ldstr    aRoleord// "roleOrd"
0x620eb  ldarg.0
0x620ec  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x620f1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x620f6  ldstr    aRoleord// "roleOrd"
0x620fb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62100  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x62105  ldloc.0
0x62106  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x6210b  ldstr    aOtype_1// "oType"
0x62110  ldarg.0
0x62111  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62116  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x6211b  ldstr    aOtype_1// "oType"
0x62120  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62125  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x6212a  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x6212f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x62134  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_DataSetControl()
0x62139  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6213e  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x62143  brfalse.s loc_62181
0x62145  ldarg.0
0x62146  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x6214b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62150  ldstr    aCustomcontrolx// "customControlXmlParam"
0x62155  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6215a  brfalse.s loc_62181
0x6215c  ldloc.0
0x6215d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62162  ldstr    aCustomcontrolx// "customControlXmlParam"
0x62167  ldarg.0
0x62168  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x6216d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62172  ldstr    aCustomcontrolx// "customControlXmlParam"
0x62177  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6217c  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x62181  ldloc.0
0x62182  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62187  ldstr    aRelationshipty// "relationshipType"
0x6218c  ldarg.0
0x6218d  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62192  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62197  ldstr    aRelationshipty// "relationshipType"
0x6219c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x621a1  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x621a6  ldloc.0
0x621a7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x621ac  ldstr    aRibboncontext_0// "ribbonContext"
0x621b1  ldarg.0
0x621b2  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x621b7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x621bc  ldstr    aRibboncontext_0// "ribbonContext"
0x621c1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x621c6  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x621cb  ldloc.0
0x621cc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x621d1  ldstr    aGridtype// "GridType"
0x621d6  ldarg.0
0x621d7  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x621dc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x621e1  ldstr    aGridtype// "GridType"
0x621e6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x621eb  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x621f0  ldloc.0
0x621f1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x621f6  ldstr    aEnablecontextu// "enableContextualActions"
0x621fb  ldarg.0
0x621fc  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62201  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62206  ldstr    aEnablecontextu// "enableContextualActions"
0x6220b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62210  brfalse.s loc_62229
0x62212  ldarg.0
0x62213  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62218  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x6221d  ldstr    aEnablecontextu// "enableContextualActions"
0x62222  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62227  br.s     loc_6222E
0x62229  ldstr    aTrue// "true"
0x6222e  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x62233  ldloc.0
0x62234  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62239  ldstr    aTeamtemplateid// "teamTemplateId"
0x6223e  ldarg.0
0x6223f  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62244  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62249  ldstr    aTeamtemplateid// "teamTemplateId"
0x6224e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62253  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x62258  ldloc.0
0x62259  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EventManager::.ctor()
0x6225e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_EventManager(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EventManager)
0x62263  ldloc.0
0x62264  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EventManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_EventManager()
0x62269  ldstr    aPageCrmeventma// "__Page_crmEventManager"
0x6226e  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x62273  ldloc.0
0x62274  ret
```
