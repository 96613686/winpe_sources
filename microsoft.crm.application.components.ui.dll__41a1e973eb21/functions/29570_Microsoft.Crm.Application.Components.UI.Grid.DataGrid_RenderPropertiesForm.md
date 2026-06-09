# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderPropertiesForm

- ea: `0x29570`
- end: `0x296bf`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderPropertiesForm`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x27750`

## callees

- `0x27020`
- `0x27060`
- `0x272d0`
- `0x272f0`
- `0x27370`
- `0x273b0`
- `0x273d0`
- `0x27540`
- `0x29570`
- `0x297b0`

## pseudocode

```c

```

## disassembly

```asm
0x29570  ldarg.1
0x29571  ldstr    aDivStyleDispla_1// "<div style=\"display:none;\" id=\"divGr"...
0x29576  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2957b  ldarg.0
0x2957c  ldarg.1
0x2957d  ldstr    aSortcolumns// "sortColumns"
0x29582  ldarg.0
0x29583  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.GridSortColumnCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_SortColumns()
0x29588  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.GridSortColumnCollection::SerializeToGridParameter()
0x2958d  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x29592  ldarg.0
0x29593  ldarg.1
0x29594  ldstr    aPagenum// "pageNum"
0x29599  ldarg.0
0x2959a  call     instance unsigned int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_CurrentPageNumber()
0x2959f  stloc.0
0x295a0  ldloca.s 0
0x295a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x295a7  call     instance string [mscorlib]System.UInt32::ToString(class [mscorlib]System.IFormatProvider)
0x295ac  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x295b1  ldarg.0
0x295b2  ldarg.1
0x295b3  ldstr    aRecsperpage// "recsPerPage"
0x295b8  ldarg.0
0x295b9  call     instance unsigned int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RecordsPerPage()
0x295be  stloc.0
0x295bf  ldloca.s 0
0x295c1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x295c6  call     instance string [mscorlib]System.UInt32::ToString(class [mscorlib]System.IFormatProvider)
0x295cb  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x295d0  ldarg.0
0x295d1  ldarg.1
0x295d2  ldstr    aDataprovider// "dataProvider"
0x295d7  ldarg.0
0x295d8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataProvider()
0x295dd  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x295e2  callvirt instance string [mscorlib]System.Type::get_FullName()
0x295e7  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x295ec  ldarg.0
0x295ed  ldarg.1
0x295ee  ldstr    aUiprovider// "uiProvider"
0x295f3  ldarg.0
0x295f4  call     instance class Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_UIProvider()
0x295f9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x295fe  callvirt instance string [mscorlib]System.Type::get_FullName()
0x29603  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x29608  ldarg.0
0x29609  ldarg.1
0x2960a  ldstr    aCols// "cols"
0x2960f  ldsfld   string [mscorlib]System.String::Empty
0x29614  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x29619  ldarg.0
0x2961a  ldarg.1
0x2961b  ldstr    aMax// "max"
0x29620  ldarg.0
0x29621  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_MaximumSelectableItems()
0x29626  stloc.1
0x29627  ldloca.s 1
0x29629  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2962e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x29633  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x29638  ldarg.0
0x29639  ldarg.1
0x2963a  ldstr    aRefreshasync// "refreshAsync"
0x2963f  ldarg.0
0x29640  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RefreshAsynchronous()
0x29645  stloc.2
0x29646  ldloca.s 2
0x29648  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2964d  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x29652  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x29657  ldarg.0
0x29658  ldarg.1
0x29659  ldstr    aPagingcookie// "pagingCookie"
0x2965e  ldarg.0
0x2965f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataProvider()
0x29664  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider::get_PagingCookie()
0x29669  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x2966e  ldarg.0
0x2966f  ldarg.1
0x29670  ldstr    aEnablemultisor// "enableMultiSort"
0x29675  ldarg.0
0x29676  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataProvider()
0x2967b  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_EnableMultiColumnSorting()
0x29680  brtrue.s loc_29689
0x29682  ldstr    aFalse// "false"
0x29687  br.s     loc_2968E
0x29689  ldstr    aTrue// "true"
0x2968e  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x29693  ldarg.0
0x29694  ldarg.1
0x29695  ldstr    aEnablepagingwh// "enablePagingWhenOnePage"
0x2969a  ldarg.0
0x2969b  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_EnablePagingWhenOnePage()
0x296a0  brtrue.s loc_296A9
0x296a2  ldstr    aFalse// "false"
0x296a7  br.s     loc_296AE
0x296a9  ldstr    aTrue// "true"
0x296ae  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFormInput(class [mscorlib]System.IO.TextWriter writer, string id, string value)
0x296b3  ldarg.1
0x296b4  ldstr    aDiv// "</div>"
0x296b9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x296be  ret
```
