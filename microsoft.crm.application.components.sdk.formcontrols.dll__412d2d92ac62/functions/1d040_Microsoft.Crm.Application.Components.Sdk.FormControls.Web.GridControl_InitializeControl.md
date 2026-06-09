# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::InitializeControl

- ea: `0x1d040`
- end: `0x1d237`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::InitializeControl`
- size: `503`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x179b0`
- `0x179f0`
- `0x17a10`
- `0x1c850`
- `0x1ca10`
- `0x1cb10`
- `0x1cb70`
- `0x1cba0`
- `0x1cc50`
- `0x1cda0`
- `0x1cde0`
- `0x1cdf0`
- `0x1ce00`
- `0x1ce20`
- `0x1ce40`
- `0x1cf30`
- `0x1d040`
- `0x1d240`
- `0x1dda0`
- `0x1e650`

## string_xrefs

- `0x1d169`: `teamTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x1d040  ldarg.0
0x1d041  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::InitializeControl()
0x1d046  ldarg.0
0x1d047  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1d04c  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ICrmFlatUIControl
0x1d051  stloc.0
0x1d052  ldloc.0
0x1d053  brfalse.s loc_1D061
0x1d055  ldarg.0
0x1d056  ldloc.0
0x1d057  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EventManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ICrmFlatUIControl::get_EventManager()
0x1d05c  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_EventManager(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EventManager)
0x1d061  ldarg.0
0x1d062  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::IsCardControl()
0x1d067  brfalse.s loc_1D07B
0x1d069  ldarg.0
0x1d06a  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.CardControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CardControl()
0x1d06f  ldarg.0
0x1d070  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1d075  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.CardControl::set_CardId(string)
0x1d07a  ret
0x1d07b  ldarg.0
0x1d07c  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_AutoExpand()
0x1d081  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d086  brfalse.s loc_1D093
0x1d088  ldarg.0
0x1d089  ldstr    aAuto_0// "Auto"
0x1d08e  stfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_autoExpand
0x1d093  ldarg.0
0x1d094  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d099  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1d09e  ldstr    aSubgridautoexp// "subgridAutoExpand"
0x1d0a3  ldarg.0
0x1d0a4  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_explicitSetAutoExpand
0x1d0a9  brfalse.s loc_1D0BD
0x1d0ab  ldarg.0
0x1d0ac  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_AutoExpand()
0x1d0b1  ldstr    aAuto_0// "Auto"
0x1d0b6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d0bb  brtrue.s loc_1D0C4
0x1d0bd  ldstr    a0// "0"
0x1d0c2  br.s     loc_1D0C9
0x1d0c4  ldstr    a1_0// "1"
0x1d0c9  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x1d0ce  ldarg.0
0x1d0cf  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1d0d4  ldarg.0
0x1d0d5  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_AutoExpand()
0x1d0da  ldstr    aFixed// "Fixed"
0x1d0df  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d0e4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_FixedSizeRows(bool)
0x1d0e9  ldarg.0
0x1d0ea  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1d0ef  ldarg.0
0x1d0f0  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x1d0f5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_TabIndex(int32)
0x1d0fa  ldarg.0
0x1d0fb  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1d100  ldarg.0
0x1d101  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1d106  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_GridId(string)
0x1d10b  ldarg.0
0x1d10c  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsRelationshipBound()
0x1d111  brfalse.s loc_1D156
0x1d113  ldarg.0
0x1d114  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d119  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1d11e  ldstr    aRelname// "relName"
0x1d123  ldarg.0
0x1d124  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_RelationshipName()
0x1d129  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x1d12e  ldarg.0
0x1d12f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d134  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1d139  ldstr    aRoleord// "roleOrd"
0x1d13e  ldarg.0
0x1d13f  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_RelationshipRoleOrdinal()
0x1d144  stloc.2
0x1d145  ldloca.s 2
0x1d147  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d14c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1d151  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x1d156  ldarg.0
0x1d157  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsTeamTemplateBound()
0x1d15c  brfalse.s loc_1D186
0x1d15e  ldarg.0
0x1d15f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d164  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x1d169  ldstr    aTeamtemplateid// "teamTemplateId"
0x1d16e  ldarg.0
0x1d16f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TeamTemplateId()
0x1d174  stloc.3
0x1d175  ldloca.s 3
0x1d177  ldstr    aB// "B"
0x1d17c  call     instance string [mscorlib]System.Guid::ToString(string)
0x1d181  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x1d186  ldarg.0
0x1d187  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsGridAvailable()
0x1d18c  brtrue.s loc_1D19C
0x1d18e  ldarg.0
0x1d18f  ldc.i4.0
0x1d190  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_ShowGridMenuBar(bool value)
0x1d195  ldarg.0
0x1d196  ldc.i4.0
0x1d197  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::set_EnableQuickFind(bool value)
0x1d19c  ldarg.0
0x1d19d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0x1d1a2  ldarg.0
0x1d1a3  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_enableSingleClick
0x1d1a8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_EnableSingleClick(bool)
0x1d1ad  ldarg.0
0x1d1ae  call     instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlRenderMode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_RenderMode()
0x1d1b3  brtrue.s loc_1D1C0
0x1d1b5  ldarg.0
0x1d1b6  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1d1bb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::SetPrintModeGridParameters()
0x1d1c0  ldarg.0
0x1d1c1  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::InitializeAppGridQueryFilter()
0x1d1c6  ldarg.0
0x1d1c7  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1d1cc  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage
0x1d1d1  stloc.1
0x1d1d2  ldloc.1
0x1d1d3  brfalse.s loc_1D1E1
0x1d1d5  ldarg.0
0x1d1d6  ldloc.1
0x1d1d7  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_PageHandlerEnabled()
0x1d1dc  stfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_pageHandlerEnabled
0x1d1e1  ldarg.0
0x1d1e2  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::_gridType
0x1d1e7  ldc.i4.4
0x1d1e8  bne.un.s loc_1D203
0x1d1ea  ldarg.0
0x1d1eb  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_IsEntityBound()
0x1d1f0  brfalse.s loc_1D203
0x1d1f2  ldarg.0
0x1d1f3  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1d1f8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationPane [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::pane
0x1d1fd  ldc.i4.0
0x1d1fe  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationPane::set_ShowUserVisualization(bool)
0x1d203  ldarg.0
0x1d204  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1d209  ldc.i4.1
0x1d20a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::set_IsSubGridMode(bool)
0x1d20f  ldarg.0
0x1d210  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsPreviewMode()
0x1d215  brtrue.s loc_1D230
0x1d217  ldarg.0
0x1d218  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsGridAvailable()
0x1d21d  brfalse.s loc_1D230
0x1d21f  ldarg.0
0x1d220  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0x1d225  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x1d22a  ldc.i4.1
0x1d22b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_IsGridFilteringEnabled(bool)
0x1d230  ldarg.0
0x1d231  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::SetGridDataProvider()
0x1d236  ret
```
