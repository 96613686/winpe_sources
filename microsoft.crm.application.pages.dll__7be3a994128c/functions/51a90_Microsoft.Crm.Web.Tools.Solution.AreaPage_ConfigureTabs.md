# Microsoft.Crm.Web.Tools.Solution.AreaPage::ConfigureTabs

- ea: `0x51a90`
- end: `0x51ff5`
- name: `Microsoft.Crm.Web.Tools.Solution.AreaPage::ConfigureTabs`
- size: `1381`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x51a90`
- `0x576b0`

## string_xrefs

- `0x51a9b`: `componentTypeFilter`
- `0x51ac5`: `componentTypeFilter`
- `0x51dab`: `componentTypeFilter`
- `0x51dce`: `componentTypeFilter`
- `0x51b45`: `areaSolutionComponent`
- `0x51d32`: `solution_solutioncomponent`
- `0x51df7`: `componentSubFilter`
- `0x51f70`: `$find({0}).add_onBeforeFormLoad(Mscrm.SolutionComponentList.launchObject)`

## pseudocode

```c

```

## disassembly

```asm
0x51a90  ldarg.0
0x51a91  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51a96  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51a9b  ldstr    aComponenttypef// "componentTypeFilter"
0x51aa0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51aa5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x51aaa  brtrue   loc_51B30
0x51aaf  ldarg.0
0x51ab0  ldtoken  [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter
0x51ab5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x51aba  ldarg.0
0x51abb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51ac0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51ac5  ldstr    aComponenttypef// "componentTypeFilter"
0x51aca  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51acf  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x51ad4  unbox.any [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter
0x51ad9  stfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter Microsoft.Crm.Web.Tools.Solution.AreaPage::selectedFilter
0x51ade  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x51ae3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x51ae8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x51aed  stloc.s  6
0x51aef  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x51af4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x51af9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MDDSolutionAwareness()
0x51afe  ldloc.s  6
0x51b00  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x51b05  brfalse.s loc_51B30
0x51b07  ldarg.0
0x51b08  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51b0d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51b12  ldstr    aRequesttype// "requestType"
0x51b17  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51b1c  ldstr    aMetadatadriven// "metadataDrivenDialog"
0x51b21  ldc.i4.3
0x51b22  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x51b27  brfalse.s loc_51B30
0x51b29  ldarg.0
0x51b2a  ldc.i4.1
0x51b2b  stfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isMetadataDrivenDialogForm
0x51b30  ldarg.0
0x51b31  ldfld    string Microsoft.Crm.Web.Tools.Solution.AreaPage::DefaultViewId
0x51b36  stloc.0
0x51b37  ldc.i4   0x1BBF
0x51b3c  stloc.1
0x51b3d  ldnull
0x51b3e  stloc.2
0x51b3f  ldarg.0
0x51b40  call     instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAreaPage::get_CurrentTabId()
0x51b45  ldstr    aAreasolutionco// "areaSolutionComponent"
0x51b4a  callvirt instance bool [mscorlib]System.String::Equals(string)
0x51b4f  ldstr    aInvalidTabName// "Invalid tab name."
0x51b54  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x51b59  ldarg.0
0x51b5a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51b5f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51b64  ldstr    aRequesttype// "requestType"
0x51b69  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51b6e  brfalse.s loc_51BA2
0x51b70  ldstr    aEntitydashboar// "entityDashboard"
0x51b75  ldarg.0
0x51b76  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51b7b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51b80  ldstr    aRequesttype// "requestType"
0x51b85  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51b8a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51b8f  call     string [mscorlib]System.Convert::ToString(string, class [mscorlib]System.IFormatProvider)
0x51b94  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51b99  brfalse.s loc_51BA2
0x51b9b  ldarg.0
0x51b9c  ldc.i4.1
0x51b9d  stfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isEntityDashboard
0x51ba2  ldc.i4.0
0x51ba3  stloc.3
0x51ba4  ldarg.0
0x51ba5  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter Microsoft.Crm.Web.Tools.Solution.AreaPage::selectedFilter
0x51baa  stloc.s  7
0x51bac  ldloc.s  7
0x51bae  ldc.i4.s 0x1D
0x51bb0  bgt.s    loc_51BC2
0x51bb2  ldloc.s  7
0x51bb4  ldc.i4.1
0x51bb5  beq.s    loc_51BE8
0x51bb7  ldloc.s  7
0x51bb9  ldc.i4.s 0x1D
0x51bbb  beq.s    loc_51BFA
0x51bbd  br       loc_51C4B
0x51bc2  ldloc.s  7
0x51bc4  ldc.i4.s 0x3D
0x51bc6  beq.s    loc_51C3C
0x51bc8  ldloc.s  7
0x51bca  ldc.i4.s 0x5B
0x51bcc  sub
0x51bcd  switch   loc_51C0C, loc_51C1E, loc_51C4B, loc_51C4B, loc_51C2D
0x51be6  br.s     loc_51C4B
0x51be8  ldarg.0
0x51be9  ldfld    string Microsoft.Crm.Web.Tools.Solution.AreaPage::EntityViewId
0x51bee  stloc.0
0x51bef  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::.ctor()
0x51bf4  stloc.2
0x51bf5  br       loc_51CA1
0x51bfa  ldarg.0
0x51bfb  ldfld    string Microsoft.Crm.Web.Tools.Solution.AreaPage::WorkflowViewId
0x51c00  stloc.0
0x51c01  ldc.i4   0x125F
0x51c06  stloc.1
0x51c07  br       loc_51CA1
0x51c0c  ldarg.0
0x51c0d  ldfld    string Microsoft.Crm.Web.Tools.Solution.AreaPage::PluginAssemblyViewId
0x51c12  stloc.0
0x51c13  ldc.i4   0x11FD
0x51c18  stloc.1
0x51c19  br       loc_51CA1
0x51c1e  ldarg.0
0x51c1f  ldfld    string Microsoft.Crm.Web.Tools.Solution.AreaPage::SdkMessageProcessingStepViewId
0x51c24  stloc.0
0x51c25  ldc.i4   0x1200
0x51c2a  stloc.1
0x51c2b  br.s     loc_51CA1
0x51c2d  ldarg.0
0x51c2e  ldfld    string Microsoft.Crm.Web.Tools.Solution.AreaPage::ServiceEndpointViewId
0x51c33  stloc.0
0x51c34  ldc.i4   0x120A
0x51c39  stloc.1
0x51c3a  br.s     loc_51CA1
0x51c3c  ldarg.0
0x51c3d  ldfld    string Microsoft.Crm.Web.Tools.Solution.AreaPage::WebResourceViewId
0x51c42  stloc.0
0x51c43  ldc.i4   0x2475
0x51c48  stloc.1
0x51c49  br.s     loc_51CA1
0x51c4b  ldarg.0
0x51c4c  ldfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isEntityDashboard
0x51c51  brfalse.s loc_51C9B
0x51c53  ldarg.0
0x51c54  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51c59  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51c5e  ldstr    aObjecttypecode_0// "objectTypeCode"
0x51c63  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51c68  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51c6d  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x51c72  stloc.3
0x51c73  ldarg.0
0x51c74  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51c79  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51c7e  ldstr    aRequesttype// "requestType"
0x51c83  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51c88  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51c8d  call     string [mscorlib]System.Convert::ToString(string, class [mscorlib]System.IFormatProvider)
0x51c92  ldloc.3
0x51c93  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::.ctor(string, int32)
0x51c98  stloc.2
0x51c99  br.s     loc_51CA1
0x51c9b  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::.ctor()
0x51ca0  stloc.2
0x51ca1  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SolutionComponentFilterSelector::.ctor()
0x51ca6  stloc.s  4
0x51ca8  ldloc.s  4
0x51caa  ldstr    aScfilter// "SCFilter"
0x51caf  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x51cb4  ldloc.s  4
0x51cb6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SolutionComponentFilterSelector::get_TypeFilterControl()
0x51cbb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x51cc0  ldstr    aSolutionFilter// "Solution.Filter.Type.All"
0x51cc5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x51cca  ldc.i4.0
0x51ccb  stloc.s  8
0x51ccd  ldloca.s 8
0x51ccf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51cd4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x51cd9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x51cde  ldloc.s  4
0x51ce0  ldarg.0
0x51ce1  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter Microsoft.Crm.Web.Tools.Solution.AreaPage::selectedFilter
0x51ce6  ldarg.0
0x51ce7  ldfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isMetadataDrivenDialogForm
0x51cec  call     void Microsoft.Crm.Web.Tools.Solution.SolutionFilterUtility::PopulateTypeFilter(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SolutionComponentFilterSelector solutionFilter, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter selectedFilter, [opt] bool isMetadataDrivenDialogForm)
0x51cf1  ldarg.0
0x51cf2  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter Microsoft.Crm.Web.Tools.Solution.AreaPage::selectedFilter
0x51cf7  ldloc.s  4
0x51cf9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SolutionComponentFilterSelector::get_SubFilterControl()
0x51cfe  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::CreateSubFilter(int32, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select)
0x51d03  ldc.i4.0
0x51d04  stloc.s  5
0x51d06  ldloc.s  4
0x51d08  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SolutionComponentFilterSelector::get_SubFilterControl()
0x51d0d  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_Selected()
0x51d12  brfalse.s loc_51D2C
0x51d14  ldloc.s  4
0x51d16  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SolutionComponentFilterSelector::get_SubFilterControl()
0x51d1b  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_Selected()
0x51d20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51d25  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x51d2a  stloc.s  5
0x51d2c  ldarg.0
0x51d2d  ldarg.0
0x51d2e  ldloc.1
0x51d2f  ldloc.0
0x51d30  ldnull
0x51d31  ldc.i4.1
0x51d32  ldstr    aSolutionSoluti_3// "solution_solutioncomponent"
0x51d37  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAreaPage::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string)
0x51d3c  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51d41  ldarg.0
0x51d42  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51d47  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51d4c  ldstr    aOid_0// "oId"
0x51d51  ldarg.0
0x51d52  call     instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAreaPage::get_CurrentObjectId()
0x51d57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x51d5c  ldarg.0
0x51d5d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51d62  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51d67  ldc.i4.1
0x51d68  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnablePaging(bool)
0x51d6d  ldarg.0
0x51d6e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51d73  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51d78  ldloc.2
0x51d79  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_DataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider)
0x51d7e  ldarg.0
0x51d7f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51d84  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51d89  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x51d8e  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridUIProvider::.ctor(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x51d93  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_UIProvider(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider)
0x51d98  ldarg.0
0x51d99  ldfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isMetadataDrivenDialogForm
0x51d9e  brfalse.s loc_51DC3
0x51da0  ldarg.0
0x51da1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51da6  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51dab  ldstr    aComponenttypef// "componentTypeFilter"
0x51db0  ldarg.0
0x51db1  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter Microsoft.Crm.Web.Tools.Solution.AreaPage::selectedFilter
0x51db6  ldc.i4.1
0x51db7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.ComponentTypeSubcode::FormatAsString(int32, int32)
0x51dbc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x51dc1  br.s     loc_51DEC
0x51dc3  ldarg.0
0x51dc4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51dc9  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51dce  ldstr    aComponenttypef// "componentTypeFilter"
0x51dd3  ldarg.0
0x51dd4  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter Microsoft.Crm.Web.Tools.Solution.AreaPage::selectedFilter
0x51dd9  stloc.s  8
0x51ddb  ldloca.s 8
0x51ddd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51de2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x51de7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x51dec  ldarg.0
0x51ded  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51df2  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51df7  ldstr    aComponentsubfi// "componentSubFilter"
0x51dfc  ldloca.s 5
0x51dfe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51e03  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x51e08  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x51e0d  ldarg.0
0x51e0e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51e13  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51e18  ldstr    aSolutionid// "solutionid"
0x51e1d  ldarg.0
0x51e1e  call     instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAreaPage::get_CurrentObjectId()
0x51e23  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x51e28  ldarg.0
0x51e29  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51e2e  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51e33  ldstr    aOtcmb// "otcmb"
0x51e38  ldc.i4   0x1BBF
0x51e3d  stloc.s  8
0x51e3f  ldloca.s 8
0x51e41  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51e46  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x51e4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x51e50  ldarg.0
0x51e51  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51e56  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51e5b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x51e60  ldstr    aRelname// "relName"
0x51e65  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51e6a  brfalse.s loc_51E86
0x51e6c  ldarg.0
0x51e6d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Web.Tools.Solution.AreaPage::areaTab
0x51e72  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x51e77  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x51e7c  ldstr    aRelname// "relName"
0x51e81  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x51e86  ldarg.0
0x51e87  ldfld    bool Microsoft.Crm.Web.Tools.Solution.AreaPage::isEntityDashboard
0x51e8c  brfalse.s loc_51EE1
0x51e8e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x51e93  ldloc.3
0x51e94  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x51e99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x51e9e  stloc.s  9
0x51ea0  ldarg.0
0x51ea1  call     instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAreaPage::get_CurrentObjectId()
0x51ea6  ldloca.s 9
0x51ea8  constrained. [mscorlib]System.Guid
  ... truncated ...
```
