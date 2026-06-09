# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::ConfigureHeader

- ea: `0x281f0`
- end: `0x2831b`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::ConfigureHeader`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x33d0`
- `0x154b0`
- `0x225f0`
- `0x23b60`
- `0x23c10`
- `0x23c50`
- `0x23cf0`
- `0x23d10`
- `0x26be0`
- `0x26c00`
- `0x26d80`
- `0x270b0`
- `0x270d0`
- `0x27690`
- `0x281f0`
- `0x28320`
- `0x2a1a0`

## pseudocode

```c

```

## disassembly

```asm
0x281f0  ldarg.0
0x281f1  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x281f6  ldarg.0
0x281f7  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_EnableGridAjaxControl()
0x281fc  brfalse.s loc_28275
0x281fe  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x28203  stloc.0
0x28204  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::.ctor()
0x28209  stloc.1
0x2820a  ldloc.1
0x2820b  ldc.i4.s 0x2A
0x2820d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Add(var<u1>)
0x28212  ldloc.1
0x28213  ldc.i4.4
0x28214  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Add(var<u1>)
0x28219  ldloc.1
0x2821a  ldc.i4.s 0x32
0x2821c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Add(var<u1>)
0x28221  ldloc.1
0x28222  ldc.i4.s 0x5F
0x28224  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Add(var<u1>)
0x28229  ldloc.1
0x2822a  ldc.i4.s 0x26
0x2822c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Add(var<u1>)
0x28231  ldloc.1
0x28232  ldc.i4.s 9
0x28234  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Add(var<u1>)
0x28239  ldloc.1
0x2823a  ldc.i4.s 0x57
0x2823c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Add(var<u1>)
0x28241  ldloc.0
0x28242  ldstr    aSubscribedeven// "subscribedEvents"
0x28247  ldloc.1
0x28248  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2824d  ldarg.0
0x2824e  ldloc.0
0x2824f  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RegisterBehavior(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x28254  ldarg.0
0x28255  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2825a  ldstr    aStaticGridGrid_1// "/_static/_grid/GridControl.js"
0x2825f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x28264  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x28269  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri file)
0x2826e  ldarg.0
0x2826f  ldloc.0
0x28270  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::ConfigureAndRegisterDataSetControl(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x28275  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBox::.ctor()
0x2827a  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x2827f  ldarg.0
0x28280  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_IsGridFilteringEnabled()
0x28285  brfalse  loc_2830F
0x2828a  ldarg.0
0x2828b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Columns()
0x28290  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x28295  stloc.2
0x28296  br.s     loc_282F1
0x28298  ldloc.2
0x28299  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2829e  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column
0x282a3  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0x282a8  isinst   Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo
0x282ad  stloc.3
0x282ae  ldloc.3
0x282af  brfalse.s loc_282F1
0x282b1  ldloc.3
0x282b2  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo::get_IsFilterable()
0x282b7  brfalse.s loc_282F1
0x282b9  ldloc.3
0x282ba  callvirt instance class Microsoft.Crm.Controls.FilterPopupContainer Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo::get_FilterPopupContainer()
0x282bf  brfalse.s loc_282F1
0x282c1  ldloc.3
0x282c2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_IsHidden()
0x282c7  brtrue.s loc_282F1
0x282c9  ldloc.3
0x282ca  callvirt instance class Microsoft.Crm.Controls.FilterPopupContainer Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo::get_FilterPopupContainer()
0x282cf  ldarg.0
0x282d0  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DeferGridFilteringInit()
0x282d5  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_DeferControlInit(bool value)
0x282da  ldarg.0
0x282db  ldloc.3
0x282dc  callvirt instance class Microsoft.Crm.Controls.FilterPopupContainer Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo::get_FilterPopupContainer()
0x282e1  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureChildControl(class Microsoft.Crm.Application.Components.UI.CrmUIControlBase child)
0x282e6  ldloc.3
0x282e7  callvirt instance class Microsoft.Crm.Controls.FilterPopupContainer Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo::get_FilterPopupContainer()
0x282ec  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x282f1  ldloc.2
0x282f2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x282f7  brtrue.s loc_28298
0x282f9  leave.s  loc_2830F
0x282fb  ldloc.2
0x282fc  isinst   [mscorlib]System.IDisposable
0x28301  stloc.s  4
0x28303  ldloc.s  4
0x28305  brfalse.s loc_2830E
0x28307  ldloc.s  4
0x28309  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2830e  endfinally
0x2830f  ldarg.0
0x28310  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x28315  call     void Microsoft.Crm.Application.Components.UI.SharedMethods::SetClientVariableHighContrastEnabled(class Microsoft.Crm.Controls.PageResourceManager headerControl)
0x2831a  ret
```
