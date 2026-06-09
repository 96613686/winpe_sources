# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderData

- ea: `0x28350`
- end: `0x2841b`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderData`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x27d60`

## callees

- `0x26d80`
- `0x27140`
- `0x272d0`
- `0x272f0`
- `0x27540`
- `0x28350`
- `0x2a2d0`
- `0x2a320`
- `0x2a360`
- `0x2a370`

## pseudocode

```c

```

## disassembly

```asm
0x28350  ldarg.0
0x28351  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Columns()
0x28356  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2835b  stloc.0
0x2835c  br.s     loc_28376
0x2835e  ldloc.0
0x2835f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x28364  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column
0x28369  stloc.1
0x2836a  ldarg.0
0x2836b  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_dataProvider
0x28370  ldloc.1
0x28371  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::AddColumn(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column)
0x28376  ldloc.0
0x28377  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2837c  brtrue.s loc_2835E
0x2837e  leave.s  loc_28391
0x28380  ldloc.0
0x28381  isinst   [mscorlib]System.IDisposable
0x28386  stloc.2
0x28387  ldloc.2
0x28388  brfalse.s loc_28390
0x2838a  ldloc.2
0x2838b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28390  endfinally
0x28391  ldarg.0
0x28392  ldfld    class Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_uiProvider
0x28397  ldarg.0
0x28398  ldftn    instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::Reraise(object sender, class Microsoft.Crm.Application.Components.UI.Grid.GridUIProviderEventArgs e)
0x2839e  newobj   instance void Microsoft.Crm.Application.Components.UI.Grid.DataReadyEventHandler::.ctor(object object, native int method)
0x283a3  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider::add_OnDataReady(class Microsoft.Crm.Application.Components.UI.Grid.DataReadyEventHandler value)
0x283a8  ldarg.0
0x283a9  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_dataProvider
0x283ae  ldarg.0
0x283af  call     instance unsigned int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_CurrentPageNumber()
0x283b4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::set_PageNumber(unsigned int32)
0x283b9  ldarg.0
0x283ba  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_dataProvider
0x283bf  ldarg.0
0x283c0  call     instance unsigned int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RecordsPerPage()
0x283c5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::set_RecordsPerPage(unsigned int32)
0x283ca  ldarg.0
0x283cb  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_dataProvider
0x283d0  ldarg.0
0x283d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.GridSortColumnCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_SortColumns()
0x283d6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::set_SortColumns(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.GridSortColumnCollection)
0x283db  ldarg.0
0x283dc  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_dataProvider
0x283e1  ldarg.0
0x283e2  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_PagingCookie()
0x283e7  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider::set_PagingCookie(string)
0x283ec  ldarg.0
0x283ed  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_dataProvider
0x283f2  ldarg.0
0x283f3  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_parameters
0x283f8  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::AddParameters(class [System]System.Collections.Specialized.NameValueCollection)
0x283fd  ldarg.0
0x283fe  ldfld    class Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_uiProvider
0x28403  ldarg.0
0x28404  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_dataProvider
0x28409  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider::set_DataSource(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider value)
0x2840e  ldarg.0
0x2840f  ldfld    class Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_uiProvider
0x28414  ldarg.1
0x28415  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider::Render(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x2841a  ret
```
