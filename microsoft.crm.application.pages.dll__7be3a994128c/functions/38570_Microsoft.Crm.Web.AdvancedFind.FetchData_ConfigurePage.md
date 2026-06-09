# Microsoft.Crm.Web.AdvancedFind.FetchData::ConfigurePage

- ea: `0x38570`
- end: `0x38946`
- name: `Microsoft.Crm.Web.AdvancedFind.FetchData::ConfigurePage`
- size: `982`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x38480`
- `0x38570`
- `0x38a60`

## string_xrefs

- `0x388e5`: `fetchXml`
- `0x385aa`: `FetchXml`
- `0x385be`: `Fetch xml must be provided to the result grid.`
- `0x38722`: `The query is not accessible.`
- `0x38827`: `LayoutXml`
- `0x388a7`: `View {0} has no FetchXml or QueryAPI on it.`

## pseudocode

```c

```

## disassembly

```asm
0x38570  ldarg.0
0x38571  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigurePage()
0x38576  ldarg.0
0x38577  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3857c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x38581  ldstr    aEntityname_2// "EntityName"
0x38586  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3858b  stloc.0
0x3858c  ldloc.0
0x3858d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x38592  ldc.i4.0
0x38593  ceq
0x38595  ldstr    aALogicalEntity// "A logical entity name must be provided "...
0x3859a  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x3859f  ldarg.0
0x385a0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x385a5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x385aa  ldstr    aFetchxml_1// "FetchXml"
0x385af  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x385b4  stloc.1
0x385b5  ldloc.1
0x385b6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x385bb  ldc.i4.0
0x385bc  ceq
0x385be  ldstr    aFetchXmlMustBe// "Fetch xml must be provided to the resul"...
0x385c3  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x385c8  ldarg.0
0x385c9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x385ce  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x385d3  ldstr    aViewid_0// "ViewId"
0x385d8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x385dd  stloc.2
0x385de  ldloc.2
0x385df  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x385e4  ldc.i4.0
0x385e5  ceq
0x385e7  ldstr    aYouMustProvide// "You must provide a view id so we don't "...
0x385ec  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x385f1  ldarg.0
0x385f2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x385f7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x385fc  ldstr    aViewtype_0// "ViewType"
0x38601  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x38606  dup
0x38607  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3860c  ldc.i4.0
0x3860d  ceq
0x3860f  ldstr    aYouMustProvide_0// "You must provide a view type for the sp"...
0x38614  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x38619  ldarg.0
0x3861a  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3861f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x38624  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x38629  ldstr    aSortcol// "SortCol"
0x3862e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x38633  stloc.3
0x38634  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38639  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3863e  stloc.s  4
0x38640  ldarg.0
0x38641  ldloc.0
0x38642  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x38647  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3864c  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x38651  ldarg.0
0x38652  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x38657  ldc.i4.1
0x38658  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_EnableAutoRefresh(bool)
0x3865d  ldarg.0
0x3865e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x38663  ldc.i4.1
0x38664  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_RefreshAsynchronous(bool)
0x38669  ldarg.0
0x3866a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x3866f  ldstr    aDisabledblclic// "disableDblClick"
0x38674  ldstr    a1// "1"
0x38679  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x3867e  ldloc.1
0x3867f  brfalse.s loc_386CB
0x38681  ldloc.1
0x38682  callvirt instance int32 [mscorlib]System.String::get_Length()
0x38687  brfalse.s loc_386CB
0x38689  ldarg.0
0x3868a  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3868f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x38694  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x38699  ldstr    aDefaultadvfind// "DefaultAdvFindViewId"
0x3869e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x386a3  stloc.2
0x386a4  ldloc.2
0x386a5  brfalse.s loc_386B7
0x386a7  ldloc.2
0x386a8  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x386ad  callvirt instance int32 [mscorlib]System.String::get_Length()
0x386b2  ldc.i4.0
0x386b3  cgt
0x386b5  br.s     loc_386B8
0x386b7  ldc.i4.0
0x386b8  ldstr    aMissingOrInval// "Missing or Invalid DefaultAdvFindViewId"...
0x386bd  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x386c2  ldc.i4   0x40F
0x386c7  stloc.s  4
0x386c9  br.s     loc_38736
0x386cb  nop
0x386cc  ldloc.2
0x386cd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x386d2  ldloc.s  4
0x386d4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ViewLoader::GetView(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x386d9  pop
0x386da  leave.s  loc_38736
0x386dc  stloc.s  7
0x386de  ldloc.s  7
0x386e0  ldarg.0
0x386e1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x386e6  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x386eb  ldc.i4.0
0x386ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x386f1  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [System]System.Uri, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x386f6  stloc.s  8
0x386f8  ldloc.s  8
0x386fa  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_ErrorCode()
0x386ff  ldc.i4   0x80040217
0x38704  beq.s    loc_38722
0x38706  ldloc.s  8
0x38708  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_ErrorCode()
0x3870d  ldc.i4   0x80048306
0x38712  beq.s    loc_38722
0x38714  ldloc.s  8
0x38716  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_ErrorCode()
0x3871b  ldc.i4   0x80040220
0x38720  bne.un.s loc_38734
0x38722  ldstr    aTheQueryIsNotA// "The query is not accessible."
0x38727  ldloc.s  7
0x38729  ldc.i4   0x8063110C
0x3872e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x38733  throw
0x38734  rethrow
0x38736  ldarg.0
0x38737  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Web.AdvancedFind.FetchData::crmGridControl
0x3873c  ldc.i4.0
0x3873d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableQuickFind(bool)
0x38742  ldarg.0
0x38743  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Web.AdvancedFind.FetchData::crmGridControl
0x38748  ldc.i4.0
0x38749  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableViewPicker(bool)
0x3874e  ldarg.0
0x3874f  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Web.AdvancedFind.FetchData::crmGridControl
0x38754  ldloc.s  4
0x38756  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x3875b  ldarg.0
0x3875c  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Web.AdvancedFind.FetchData::crmGridControl
0x38761  ldloc.2
0x38762  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x38767  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ViewId(valuetype [mscorlib]System.Guid)
0x3876c  ldarg.0
0x3876d  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Web.AdvancedFind.FetchData::crmGridControl
0x38772  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x38777  ldloc.2
0x38778  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0x3877d  ldarg.0
0x3877e  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Web.AdvancedFind.FetchData::crmGridControl
0x38783  ldarg.0
0x38784  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x38789  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x3878e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_TargetEntityType(string)
0x38793  ldarg.0
0x38794  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Web.AdvancedFind.FetchData::crmGridControl
0x38799  ldstr    aGrid_0// "Grid"
0x3879e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ChartGridMode(string)
0x387a3  ldarg.0
0x387a4  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Web.AdvancedFind.FetchData::crmGridControl
0x387a9  ldstr    aSubgridstandar// "SubGridStandard"
0x387ae  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_RibbonContextType(string)
0x387b3  ldarg.0
0x387b4  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Web.AdvancedFind.FetchData::crmGridControl
0x387b9  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x387be  ldstr    asc_11EF2A// ""
0x387c3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_StylePosition(string)
0x387c8  ldarg.0
0x387c9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x387ce  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x387d3  ldstr    aDataprovider_0// "DataProvider"
0x387d8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x387dd  stloc.s  5
0x387df  ldloc.s  5
0x387e1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x387e6  brtrue.s loc_38801
0x387e8  ldarg.0
0x387e9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x387ee  ldloc.s  5
0x387f0  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x387f5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridProviderFactory::CreateDataProvider(string, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x387fa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_DataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider)
0x387ff  br.s     loc_3881C
0x38801  ldarg.0
0x38802  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x38807  ldarg.0
0x38808  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x3880d  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x38812  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridProviderFactory::CreateDataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x38817  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_DataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider)
0x3881c  ldarg.0
0x3881d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x38822  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x38827  ldstr    aLayoutxml_0// "LayoutXml"
0x3882c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x38831  stloc.s  6
0x38833  ldloc.s  6
0x38835  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3883a  brfalse.s loc_3884E
0x3883c  ldarg.0
0x3883d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x38842  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x38847  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewUtility::GetDefaultLayoutXml(int32)
0x3884c  stloc.s  6
0x3884e  ldarg.0
0x3884f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x38854  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_View()
0x38859  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_QueryApi()
0x3885e  brfalse.s loc_3887A
0x38860  ldarg.0
0x38861  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x38866  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_View()
0x3886b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_QueryApi()
0x38870  callvirt instance int32 [mscorlib]System.String::get_Length()
0x38875  brtrue   loc_38926
0x3887a  ldarg.0
0x3887b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x38880  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_View()
0x38885  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_FetchXml()
0x3888a  brfalse.s loc_388A6
0x3888c  ldarg.0
0x3888d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x38892  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_View()
0x38897  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_FetchXml()
0x3889c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x388a1  ldc.i4.0
0x388a2  cgt.un
0x388a4  br.s     loc_388A7
0x388a6  ldc.i4.0
0x388a7  ldstr    aView0HasNoFetc// "View {0} has no FetchXml or QueryAPI on"...
0x388ac  ldc.i4.1
0x388ad  newarr   [mscorlib]System.Object
0x388b2  dup
0x388b3  ldc.i4.0
0x388b4  ldloc.2
0x388b5  stelem.ref
0x388b6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string, object[])
0x388bb  ldarg.0
0x388bc  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x388c1  ldc.i4.0
0x388c2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_SuppressFetch(bool)
0x388c7  ldarg.0
0x388c8  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x388cd  ldc.i4.0
0x388ce  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0x388d3  ldarg.0
0x388d4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x388d9  ldc.i4.0
0x388da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_IsGridFilteringEnabled(bool)
0x388df  ldarg.0
0x388e0  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x388e5  ldstr    aFetchxml// "fetchXml"
0x388ea  ldloc.1
0x388eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x388f0  ldarg.0
0x388f1  ldloc.s  6
0x388f3  ldloc.1
0x388f4  call     instance void Microsoft.Crm.Web.AdvancedFind.FetchData::SetGridColumns(string layoutXml, string fetchXml)
0x388f9  ldloc.3
0x388fa  brfalse.s loc_38926
0x388fc  ldloc.3
0x388fd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x38902  ldc.i4.0
0x38903  ble.s    loc_38926
0x38905  ldarg.0
0x38906  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x3890b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.GridSortColumnCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_SortColumns()
0x38910  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryColumnSortInfo>::Clear()
0x38915  ldarg.0
0x38916  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x3891b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.GridSortColumnCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_SortColumns()
0x38920  ldloc.3
0x38921  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.GridSortColumnCollection::DeserializeFromGridParameter(string)
0x38926  ldarg.0
0x38927  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.AdvancedFind.FetchData::get_crmGrid()
0x3892c  ldstr    aViewtitle// "viewTitle"
0x38931  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x38936  ldstr    aAdvancedfindse// "AdvancedFindSearchResultsViewName"
0x3893b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x38940  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x38945  ret
```
