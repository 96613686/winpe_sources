# Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage_3

- ea: `0xcc7c0`
- end: `0xcca2e`
- name: `Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage_3`
- size: `622`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0xcc200`
- `0xcc700`
- `0xcc7a0`
- `0xd51e0`
- `0xd5890`

## callees

- `0xcbbb0`
- `0xcbbe0`
- `0xcbf90`
- `0xcc7c0`
- `0xcca70`

## string_xrefs

- `0xcc9d3`: `security`
- `0xcc98b`: `customControlXmlParam`
- `0xcc99b`: `customControlXmlParam`
- `0xcc9e1`: `Bad PrivilegeId passed in from entity form`

## pseudocode

```c

```

## disassembly

```asm
0xcc7c0  ldarg.0
0xcc7c1  ldarg.1
0xcc7c2  call     instance bool Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::HasPrivilegesToSeeGrid(int32 objectTypeCode)
0xcc7c7  brfalse  loc_CCA2C
0xcc7cc  ldarg.0
0xcc7cd  call     instance string Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentObjectTypeCode()
0xcc7d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcc7d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcc7dc  stloc.0
0xcc7dd  ldloc.0
0xcc7de  ldarg.0
0xcc7df  call     instance string Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentObjectId()
0xcc7e4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xcc7e9  ldstr    aCrmgrid// "crmGrid"
0xcc7ee  stloc.1
0xcc7ef  ldarg.s  5
0xcc7f1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcc7f6  brtrue.s loc_CC806
0xcc7f8  ldloc.1
0xcc7f9  ldstr    asc_12B0EE// "_"
0xcc7fe  ldarg.s  5
0xcc800  call     string [mscorlib]System.String::Concat(string, string, string)
0xcc805  stloc.1
0xcc806  ldloc.1
0xcc807  ldstr    aE7a8127886354d// "{E7A81278-8635-4d9e-8D4D-59480B391C5B}"
0xcc80c  ldc.i4.0
0xcc80d  ldsfld   string [mscorlib]System.String::Empty
0xcc812  ldnull
0xcc813  ldnull
0xcc814  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcc819  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::.ctor(string, string, bool, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcc81e  stloc.2
0xcc81f  ldarg.0
0xcc820  call     instance class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_Request()
0xcc825  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xcc82a  ldstr    aInlineedit// "inlineEdit"
0xcc82f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcc834  stloc.3
0xcc835  ldnull
0xcc836  stloc.s  4
0xcc838  ldloc.3
0xcc839  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcc83e  brtrue.s loc_CC85D
0xcc840  ldloc.3
0xcc841  ldstr    a1// "1"
0xcc846  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcc84b  brfalse.s loc_CC85D
0xcc84d  ldloc.2
0xcc84e  ldc.i4.3
0xcc84f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ControlActivator::CreateControl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor)
0xcc854  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl
0xcc859  stloc.s  4
0xcc85b  br.s     loc_CC86A
0xcc85d  ldloc.2
0xcc85e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ControlActivator::CreateControl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor)
0xcc863  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl
0xcc868  stloc.s  4
0xcc86a  ldloc.s  4
0xcc86c  ldarg.s  4
0xcc86e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_GridType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0xcc873  ldloc.s  4
0xcc875  ldloc.0
0xcc876  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_DataSource(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xcc87b  ldloc.s  4
0xcc87d  ldarg.1
0xcc87e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcc883  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcc888  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xcc88d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_TargetEntityType(string)
0xcc892  ldloc.s  4
0xcc894  ldarg.2
0xcc895  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xcc89a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_ViewId(valuetype [mscorlib]System.Guid)
0xcc89f  ldloc.s  4
0xcc8a1  ldc.i4.1
0xcc8a2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_EnableJumpBar(bool)
0xcc8a7  ldloc.s  4
0xcc8a9  ldarg.s  5
0xcc8ab  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_RelationshipName(string)
0xcc8b0  ldloc.s  4
0xcc8b2  ldarg.s  7
0xcc8b4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_RelationshipRoleOrdinal(int32)
0xcc8b9  ldarg.0
0xcc8ba  call     instance class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_Request()
0xcc8bf  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xcc8c4  ldstr    aRof// "rof"
0xcc8c9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcc8ce  call     bool [mscorlib]System.Boolean::Parse(string)
0xcc8d3  brfalse.s loc_CC8DD
0xcc8d5  ldloc.s  4
0xcc8d7  ldc.i4.1
0xcc8d8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_IsCommandBarEnabled(bool)
0xcc8dd  ldloc.s  4
0xcc8df  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::get_CompositeControl()
0xcc8e4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0xcc8e9  ldarg.3
0xcc8ea  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_QueryApi(string)
0xcc8ef  ldloc.s  4
0xcc8f1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::get_CompositeControl()
0xcc8f6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0xcc8fb  ldc.i4.1
0xcc8fc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnablePaging(bool)
0xcc901  ldloc.s  4
0xcc903  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::get_CompositeControl()
0xcc908  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0xcc90d  ldstr    aOid_0// "oId"
0xcc912  ldarg.0
0xcc913  call     instance string Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentObjectId()
0xcc918  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xcc91d  ldloc.s  4
0xcc91f  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::get_CompositeControl()
0xcc924  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0xcc929  ldstr    aOtype// "oType"
0xcc92e  ldarg.0
0xcc92f  call     instance string Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentObjectTypeCode()
0xcc934  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xcc939  ldloc.s  4
0xcc93b  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::get_CompositeControl()
0xcc940  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0xcc945  ldstr    aIscustomrelati// "isCustomRelationship"
0xcc94a  ldarg.s  6
0xcc94c  brtrue.s loc_CC955
0xcc94e  ldstr    aFalse// "false"
0xcc953  br.s     loc_CC95A
0xcc955  ldstr    aTrue_0// "true"
0xcc95a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xcc95f  ldarg.s  4
0xcc961  ldc.i4.1
0xcc962  bne.un.s loc_CC9AA
0xcc964  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xcc969  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xcc96e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_DataSetControl()
0xcc973  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcc978  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcc97d  brfalse.s loc_CC9AA
0xcc97f  ldloc.s  4
0xcc981  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::get_CompositeControl()
0xcc986  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0xcc98b  ldstr    aCustomcontrolx// "customControlXmlParam"
0xcc990  ldarg.0
0xcc991  call     instance class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_Request()
0xcc996  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xcc99b  ldstr    aCustomcontrolx// "customControlXmlParam"
0xcc9a0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcc9a5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xcc9aa  ldloc.s  4
0xcc9ac  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::get_GridMenuBar()
0xcc9b1  ldarg.s  5
0xcc9b3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::set_RelationshipName(string)
0xcc9b8  ldarg.1
0xcc9b9  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData::IsUsingRibbon(int32)
0xcc9be  brfalse.s loc_CC9C8
0xcc9c0  ldloc.s  4
0xcc9c2  ldc.i4.0
0xcc9c3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_ShowGridMenuBar(bool)
0xcc9c8  ldarg.0
0xcc9c9  call     instance class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_Request()
0xcc9ce  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xcc9d3  ldstr    aSecurity// "security"
0xcc9d8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcc9dd  dup
0xcc9de  ldnull
0xcc9df  cgt.un
0xcc9e1  ldstr    aBadPrivilegeid// "Bad PrivilegeId passed in from entity f"...
0xcc9e6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xcc9eb  ldc.i4.7
0xcc9ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcc9f1  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0xcc9f6  stloc.s  5
0xcc9f8  ldloc.s  4
0xcc9fa  ldloc.s  5
0xcc9fc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_MenuAccessRights(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights)
0xcca01  ldarg.0
0xcca02  ldloc.s  4
0xcca04  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::.ctor(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl)
0xcca09  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::_areaTab
0xcca0e  ldarg.0
0xcca0f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::_pageManager
0xcca14  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xcca19  ldloc.s  4
0xcca1b  isinst   [System.Web]System.Web.UI.Control
0xcca20  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xcca25  ldarg.0
0xcca26  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::_areaTab
0xcca2b  ret
0xcca2c  ldnull
0xcca2d  ret
```
