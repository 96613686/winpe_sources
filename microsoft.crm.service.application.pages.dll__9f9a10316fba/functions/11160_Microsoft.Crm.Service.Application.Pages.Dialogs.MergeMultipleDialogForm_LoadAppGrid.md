# Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::LoadAppGrid

- ea: `0x11160`
- end: `0x112e0`
- name: `Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::LoadAppGrid`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x10d30`

## callees

- `0x10d20`

## pseudocode

```c

```

## disassembly

```asm
0x11160  ldarg.2
0x11161  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x11166  ldc.i4   0x40F
0x1116b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ViewLoader::GetView(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x11170  stloc.0
0x11171  ldarg.0
0x11172  ldloc.0
0x11173  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_FetchXml()
0x11178  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x1117d  stfld    string Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::fetchXml
0x11182  ldarg.0
0x11183  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x11188  ldc.i4.0
0x11189  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableQuickFind(bool)
0x1118e  ldarg.0
0x1118f  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x11194  ldc.i4.0
0x11195  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableViewPicker(bool)
0x1119a  ldarg.0
0x1119b  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x111a0  ldc.i4   0x40F
0x111a5  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x111aa  ldarg.0
0x111ab  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x111b0  ldarg.2
0x111b1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x111b6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ViewId(valuetype [mscorlib]System.Guid)
0x111bb  ldarg.0
0x111bc  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x111c1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x111c6  ldc.i4.0
0x111c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnableRefresh(bool)
0x111cc  ldarg.0
0x111cd  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x111d2  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x111d7  ldc.i4.0
0x111d8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0x111dd  ldarg.0
0x111de  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x111e3  ldc.i4.0
0x111e4  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ShowGridMenuBar(bool)
0x111e9  ldarg.0
0x111ea  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x111ef  ldarg.0
0x111f0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x111f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x111fa  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_TargetEntityType(string)
0x111ff  ldarg.0
0x11200  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x11205  ldstr    aGrid// "Grid"
0x1120a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ChartGridMode(string)
0x1120f  ldarg.0
0x11210  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x11215  ldstr    aSubgridstandar// "SubGridStandard"
0x1121a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_RibbonContextType(string)
0x1121f  ldarg.0
0x11220  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x11225  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1122a  ldc.i4.1
0x1122b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_MaximumSelectableItems(int32)
0x11230  ldarg.0
0x11231  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x11236  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1123b  ldstr    asc_15D82// ""
0x11240  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_StylePosition(string)
0x11245  ldarg.0
0x11246  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::get_crmGrid()
0x1124b  ldarg.0
0x1124c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x11251  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x11256  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridProviderFactory::CreateDataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x1125b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_DataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider)
0x11260  ldarg.0
0x11261  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x11266  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1126b  ldc.i4.0
0x1126c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_SuppressFetch(bool)
0x11271  ldarg.0
0x11272  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x11277  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1127c  ldc.i4.0
0x1127d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_IsGridFilteringEnabled(bool)
0x11282  ldarg.0
0x11283  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x11288  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1128d  ldc.i4.0
0x1128e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_EnableAutoRefresh(bool)
0x11293  ldarg.0
0x11294  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x11299  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1129e  ldc.i4.0
0x1129f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_RefreshAsynchronous(bool)
0x112a4  ldarg.0
0x112a5  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::crmGridControl
0x112aa  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x112af  ldstr    aDisabledblclic// "disableDblClick"
0x112b4  ldstr    a1// "1"
0x112b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x112be  ldarg.0
0x112bf  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::get_crmGrid()
0x112c4  ldstr    aDisablecontext// "DisableContextMenu"
0x112c9  ldstr    a1// "1"
0x112ce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x112d3  ldarg.0
0x112d4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::get_crmGrid()
0x112d9  ldarg.1
0x112da  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_EmptyGridMessage(string)
0x112df  ret
```
