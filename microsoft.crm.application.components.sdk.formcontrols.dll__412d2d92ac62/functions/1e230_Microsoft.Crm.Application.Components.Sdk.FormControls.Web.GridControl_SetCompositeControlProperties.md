# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetCompositeControlProperties

- ea: `0x1e230`
- end: `0x1e505`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetCompositeControlProperties`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1d330`

## callees

- `0x1c7f0`
- `0x1c8a0`
- `0x1c960`
- `0x1c980`
- `0x1c9f0`
- `0x1cb30`
- `0x1cba0`
- `0x1cbc0`
- `0x1cbe0`
- `0x1cc10`
- `0x1cc70`
- `0x1cd30`
- `0x1cda0`
- `0x1cdc0`
- `0x1cde0`
- `0x1ce20`
- `0x1cf00`
- `0x1e230`
- `0x1e510`
- `0x1e530`
- `0x1e540`
- `0x1e5f0`

## pseudocode

```c

```

## disassembly

```asm
0x1e230  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e235  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e23a  ldarg.0
0x1e23b  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0x1e240  ldc.i4.1
0x1e241  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1e246  stloc.0
0x1e247  ldloc.0
0x1e248  brtrue.s loc_1E24D
0x1e24a  ldc.i4.1
0x1e24b  br.s     loc_1E24E
0x1e24d  ldc.i4.0
0x1e24e  stloc.1
0x1e24f  ldloc.1
0x1e250  brtrue   loc_1E3A8
0x1e255  ldarg.0
0x1e256  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_RowsToRender()
0x1e25b  ldc.i4.0
0x1e25c  ble.s    loc_1E26F
0x1e25e  ldarg.0
0x1e25f  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e264  ldarg.0
0x1e265  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_RowsToRender()
0x1e26a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_RowsToRender(int32)
0x1e26f  ldarg.0
0x1e270  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e275  ldarg.0
0x1e276  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_MaxRowsBeforeScroll()
0x1e27b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_MaxRowsBeforeScroll(int32)
0x1e280  ldarg.0
0x1e281  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e286  ldarg.0
0x1e287  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ViewType()
0x1e28c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x1e291  ldarg.0
0x1e292  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e297  ldarg.0
0x1e298  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ViewId()
0x1e29d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1e2a2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_ViewId(string)
0x1e2a7  ldarg.0
0x1e2a8  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsChartAvailable()
0x1e2ad  brfalse.s loc_1E2D4
0x1e2af  ldarg.0
0x1e2b0  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e2b5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationPane [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::pane
0x1e2ba  ldstr    aViewtitle// "viewTitle"
0x1e2bf  ldarg.0
0x1e2c0  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1e2c5  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_View()
0x1e2ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_Title()
0x1e2cf  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationPane::SetParameter(string, string)
0x1e2d4  ldarg.0
0x1e2d5  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e2da  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_IsDashboardComponent()
0x1e2df  brfalse  loc_1E3A8
0x1e2e4  ldarg.0
0x1e2e5  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e2ea  ldarg.0
0x1e2eb  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsGridAvailable()
0x1e2f0  brtrue.s loc_1E2FA
0x1e2f2  ldarg.0
0x1e2f3  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableViewPicker()
0x1e2f8  br.s     loc_1E2FB
0x1e2fa  ldc.i4.1
0x1e2fb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_IsAppGridRequired(bool)
0x1e300  ldarg.0
0x1e301  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_QueryFilter()
0x1e306  ldc.i4.5
0x1e307  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter::set_RenderMode(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlRenderMode)
0x1e30c  ldarg.0
0x1e30d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1e312  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_ViewEntityTypeName()
0x1e317  ldarg.0
0x1e318  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0x1e31d  call     bool [mscorlib]System.String::Equals(string, string)
0x1e322  brtrue.s loc_1E327
0x1e324  ldc.i4.2
0x1e325  br.s     loc_1E328
0x1e327  ldc.i4.0
0x1e328  stloc.1
0x1e329  ldloc.1
0x1e32a  brtrue.s loc_1E3A8
0x1e32c  ldarg.0
0x1e32d  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsGridAvailable()
0x1e332  brtrue.s loc_1E3A8
0x1e334  ldarg.0
0x1e335  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_VisualizationId()
0x1e33a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e33f  brtrue.s loc_1E3A8
0x1e341  ldc.i4.2
0x1e342  newarr   [mscorlib]System.String
0x1e347  dup
0x1e348  ldc.i4.0
0x1e349  ldstr    aName// "name"
0x1e34e  stelem.ref
0x1e34f  dup
0x1e350  ldc.i4.1
0x1e351  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x1e356  stelem.ref
0x1e357  stloc.2
0x1e358  ldarg.0
0x1e359  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsUserChart()
0x1e35e  brtrue.s loc_1E367
0x1e360  ldc.i4   0x457
0x1e365  br.s     loc_1E36C
0x1e367  ldc.i4   0x458
0x1e36c  stloc.3
0x1e36d  ldarg.0
0x1e36e  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_VisualizationId()
0x1e373  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1e378  ldloc.3
0x1e379  ldloc.2
0x1e37a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAppHelper::RetrieveVisualization(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.VisualizationType, string[])
0x1e37f  stloc.s  4
0x1e381  ldloc.s  4
0x1e383  brfalse.s loc_1E3A8
0x1e385  ldloc.s  4
0x1e387  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x1e38c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1e391  castclass [mscorlib]System.String
0x1e396  ldarg.0
0x1e397  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0x1e39c  call     bool [mscorlib]System.String::Equals(string, string)
0x1e3a1  brtrue.s loc_1E3A6
0x1e3a3  ldc.i4.2
0x1e3a4  br.s     loc_1E3A7
0x1e3a6  ldc.i4.0
0x1e3a7  stloc.1
0x1e3a8  ldloc.1
0x1e3a9  brtrue.s loc_1E3EE
0x1e3ab  ldarg.0
0x1e3ac  ldarg.0
0x1e3ad  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0x1e3b2  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::PrivilegeCheckNeeded(string entityName)
0x1e3b7  brfalse.s loc_1E3DE
0x1e3b9  ldarg.0
0x1e3ba  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0x1e3bf  ldc.i4.1
0x1e3c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e3c5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e3ca  brtrue.s loc_1E3DE
0x1e3cc  ldarg.0
0x1e3cd  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e3d2  ldarg.0
0x1e3d3  ldc.i4.3
0x1e3d4  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::GetErrorMessage(valuetype Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ErrorCode errorCode)
0x1e3d9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_EmptyMessage(string)
0x1e3de  ldarg.0
0x1e3df  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsChartAvailable()
0x1e3e4  brfalse.s loc_1E41F
0x1e3e6  ldarg.0
0x1e3e7  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetPaneProperties()
0x1e3ec  br.s     loc_1E41F
0x1e3ee  ldloc.0
0x1e3ef  brtrue.s loc_1E3F4
0x1e3f1  ldnull
0x1e3f2  br.s     loc_1E40E
0x1e3f4  ldloc.0
0x1e3f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x1e3fa  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1e3ff  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1e404  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e409  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e40e  stloc.s  5
0x1e410  ldarg.0
0x1e411  ldloc.1
0x1e412  ldloc.s  5
0x1e414  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::GetErrorMessage(valuetype Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ErrorCode errorCode, string formatArgs)
0x1e419  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1e41e  throw
0x1e41f  leave    loc_1E504
0x1e424  stloc.s  6
0x1e426  ldarg.0
0x1e427  ldc.i4.0
0x1e428  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableChartPicker(bool value)
0x1e42d  ldarg.0
0x1e42e  ldc.i4.0
0x1e42f  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableJumpBar(bool value)
0x1e434  ldarg.0
0x1e435  ldc.i4.0
0x1e436  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableQuickFind(bool value)
0x1e43b  ldarg.0
0x1e43c  ldc.i4.0
0x1e43d  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableViewPicker(bool value)
0x1e442  ldarg.0
0x1e443  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1e448  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e44d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::SetEmptyView(valuetype [mscorlib]System.Guid)
0x1e452  ldarg.0
0x1e453  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e458  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e45d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1e462  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_ViewId(string)
0x1e467  ldarg.0
0x1e468  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e46d  ldc.i4.1
0x1e46e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_RequiredElements(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RequiredElementsMask)
0x1e473  ldarg.0
0x1e474  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1e479  ldc.i4.1
0x1e47a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_IsSubGridMode(bool)
0x1e47f  ldarg.0
0x1e480  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1e485  ldc.i4.0
0x1e486  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnableRefresh(bool)
0x1e48b  ldarg.0
0x1e48c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1e491  ldc.i4.0
0x1e492  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnableColumnHeader(bool)
0x1e497  ldarg.0
0x1e498  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1e49d  ldc.i4.0
0x1e49e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnableColumnSorting(bool)
0x1e4a3  ldloc.1
0x1e4a4  brfalse.s loc_1E4B1
0x1e4a6  ldloc.s  6
0x1e4a8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1e4ad  stloc.s  7
0x1e4af  br.s     loc_1E4DB
0x1e4b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1e4b6  ldloc.s  6
0x1e4b8  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x1e4bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e4c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetErrorMessageWithoutEncoding(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e4c7  stloc.s  7
0x1e4c9  ldloc.s  7
0x1e4cb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e4d0  brfalse.s loc_1E4DB
0x1e4d2  ldarg.0
0x1e4d3  ldc.i4.4
0x1e4d4  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::GetErrorMessage(valuetype Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ErrorCode errorCode)
0x1e4d9  stloc.s  7
0x1e4db  ldarg.0
0x1e4dc  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1e4e1  ldstr    aEmptyview// "EmptyView"
0x1e4e6  ldstr    a1_0// "1"
0x1e4eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x1e4f0  ldarg.0
0x1e4f1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1e4f6  ldstr    aEmptyviewmessa// "EmptyViewMessage"
0x1e4fb  ldloc.s  7
0x1e4fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x1e502  leave.s  loc_1E504
0x1e504  ret
```
