# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderErrorInnerHtml

- ea: `0x27f60`
- end: `0x28059`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderErrorInnerHtml`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x27d60`

## callees

- `0xc740`
- `0xc760`
- `0x26be0`
- `0x26c00`
- `0x26d80`
- `0x26fd0`
- `0x270d0`
- `0x27100`
- `0x27f60`

## pseudocode

```c

```

## disassembly

```asm
0x27f60  ldarg.1
0x27f61  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x27f66  stloc.0
0x27f67  ldloc.0
0x27f68  ldstr    aTableCellspaci_1// "<table cellSpacing=0 cellPadding=0 clas"...
0x27f6d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27f72  ldloc.0
0x27f73  ldstr    aTrTdTdTrTable// "<tr><td></td></tr></table>"
0x27f78  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27f7d  ldarg.0
0x27f7e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Columns()
0x27f83  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x27f88  stloc.1
0x27f89  br       loc_28030
0x27f8e  ldloc.1
0x27f8f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x27f94  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column
0x27f99  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0x27f9e  isinst   Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo
0x27fa3  stloc.2
0x27fa4  ldarg.0
0x27fa5  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_IsGridFilteringEnabled()
0x27faa  brfalse  loc_28030
0x27faf  ldloc.2
0x27fb0  brfalse.s loc_28030
0x27fb2  ldloc.2
0x27fb3  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo::get_IsFilterable()
0x27fb8  brfalse.s loc_28030
0x27fba  ldloc.2
0x27fbb  callvirt instance class Microsoft.Crm.Controls.FilterPopupContainer Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo::get_FilterPopupContainer()
0x27fc0  brfalse.s loc_28030
0x27fc2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x27fc7  stloc.3
0x27fc8  ldloc.3
0x27fc9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27fce  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x27fd3  stloc.s  4
0x27fd5  ldloc.s  4
0x27fd7  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x27fdc  stloc.s  5
0x27fde  ldloc.2
0x27fdf  callvirt instance class Microsoft.Crm.Controls.FilterPopupContainer Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo::get_FilterPopupContainer()
0x27fe4  ldarg.0
0x27fe5  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TabIndex()
0x27fea  stloc.s  6
0x27fec  ldloca.s 6
0x27fee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27ff3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x27ff8  callvirt instance void Microsoft.Crm.Controls.FilterPopupContainer::set_PopupTabIndex(string value)
0x27ffd  ldloc.2
0x27ffe  callvirt instance class Microsoft.Crm.Controls.FilterPopupContainer Microsoft.Crm.Application.Components.UI.Grid.AppGridColumnUIInfo::get_FilterPopupContainer()
0x28003  ldloc.s  5
0x28005  callvirt instance void Microsoft.Crm.Controls.FilterPopupContainer::RenderFilterContainer(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x2800a  ldloc.0
0x2800b  ldloc.3
0x2800c  callvirt instance string [mscorlib]System.Object::ToString()
0x28011  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x28016  leave.s  loc_28030
0x28018  ldloc.s  5
0x2801a  brfalse.s loc_28023
0x2801c  ldloc.s  5
0x2801e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28023  endfinally
0x28024  ldloc.s  4
0x28026  brfalse.s loc_2802F
0x28028  ldloc.s  4
0x2802a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2802f  endfinally
0x28030  ldloc.1
0x28031  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x28036  brtrue   loc_27F8E
0x2803b  leave.s  loc_28051
0x2803d  ldloc.1
0x2803e  isinst   [mscorlib]System.IDisposable
0x28043  stloc.s  7
0x28045  ldloc.s  7
0x28047  brfalse.s loc_28050
0x28049  ldloc.s  7
0x2804b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28050  endfinally
0x28051  ldarg.0
0x28052  ldc.i4.0
0x28053  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_IsGridFilteringEnabled(bool value)
0x28058  ret
```
