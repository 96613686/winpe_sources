# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderColumnHeader

- ea: `0x284a0`
- end: `0x29263`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderColumnHeader`
- size: `3523`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x27d60`

## callees

- `0xc740`
- `0xc760`
- `0x1a0a0`
- `0x1a0d0`
- `0x1a350`
- `0x1a390`
- `0x26be0`
- `0x26c00`
- `0x26d30`
- `0x26d80`
- `0x26f30`
- `0x26fd0`
- `0x270d0`
- `0x27160`
- `0x27270`
- `0x27290`
- `0x27330`
- `0x27340`
- `0x27370`
- `0x27540`
- `0x276e0`
- `0x27740`
- `0x27b70`
- `0x27d30`
- `0x28480`
- `0x284a0`
- `0x29270`
- `0x29290`
- `0x292a0`
- `0x292b0`
- `0x29330`
- `0x294e0`
- `0x29540`
- `0x2a170`
- `0x2a1b0`

## string_xrefs

- `0x28e1a`: `Grid.Common.Alt.SortedColumn.Down`
- `0x28da6`: `Grid.Common.Alt.SortedColumn.Up`
- `0x28e2b`: `Grid.Common.Alt.SortedColumn.Up`
- `0x284ac`: `Grid.Common.HeaderTableSummary`

## pseudocode

```c

```

## disassembly

```asm
0x284a0  ldarg.1
0x284a1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x284a6  stloc.0
0x284a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x284ac  ldstr    aGridCommonHead// "Grid.Common.HeaderTableSummary"
0x284b1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x284b6  stloc.1
0x284b7  ldloc.0
0x284b8  ldc.i4.7
0x284b9  newarr   [mscorlib]System.String
0x284be  dup
0x284bf  ldc.i4.0
0x284c0  ldstr    aTableCellspaci_2// "<table cellSpacing=0 cellPadding=0 id="...
0x284c5  stelem.ref
0x284c6  dup
0x284c7  ldc.i4.1
0x284c8  ldarg.0
0x284c9  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x284ce  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x284d3  stelem.ref
0x284d4  dup
0x284d5  ldc.i4.2
0x284d6  ldstr    aGridbarRolePre// "_gridBar\" role=\"presentation\" class="...
0x284db  stelem.ref
0x284dc  dup
0x284dd  ldc.i4.3
0x284de  ldarg.0
0x284df  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_CssSuffix()
0x284e4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x284e9  stelem.ref
0x284ea  dup
0x284eb  ldc.i4.4
0x284ec  ldstr    a0Summary// " {0}\" summary=\""
0x284f1  stelem.ref
0x284f2  dup
0x284f3  ldc.i4.5
0x284f4  ldloc.1
0x284f5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x284fa  stelem.ref
0x284fb  dup
0x284fc  ldc.i4.6
0x284fd  ldstr    asc_57122// "\" >"
0x28502  stelem.ref
0x28503  call     string [mscorlib]System.String::Concat(string[])
0x28508  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2850d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x28512  brtrue.s loc_2851B
0x28514  ldstr    asc_3280A// ""
0x28519  br.s     loc_28520
0x2851b  ldstr    aMsCrmGridHeade// "ms-crm-Grid-HeaderBackColor"
0x28520  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x28525  ldloc.0
0x28526  ldstr    aColgroup// "<colgroup"
0x2852b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x28530  ldstr    aId// "id"
0x28535  ldarg.0
0x28536  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2853b  ldstr    aGridbarcols// "_gridBarCols"
0x28540  call     string [mscorlib]System.String::Concat(string, string)
0x28545  ldarg.1
0x28546  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2854b  ldloc.0
0x2854c  ldc.i4.s 0x3E
0x2854e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x28553  ldarg.0
0x28554  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_MaximumSelectableItems()
0x28559  brfalse.s loc_2857A
0x2855b  ldarg.0
0x2855c  ldarg.0
0x2855d  call     instance unsigned int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_LeftColumnWidth()
0x28562  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x28567  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2856c  brtrue.s loc_28572
0x2856e  ldc.i4.s 0x12
0x28570  br.s     loc_28574
0x28572  ldc.i4.s 0x28
0x28574  add
0x28575  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_LeftColumnWidth(unsigned int32 value)
0x2857a  ldarg.0
0x2857b  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x28580  ldstr    aOtc// "otc"
0x28585  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2858a  ldloca.s 2
0x2858c  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x28591  brfalse.s loc_285A4
0x28593  ldarg.0
0x28594  ldloc.2
0x28595  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2859a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.MetadataHierarchyEnable::IsEntityHierarchyEnabled(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2859f  stfld    bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::_isEntityHierarchyEnable
0x285a4  ldarg.0
0x285a5  call     instance unsigned int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_LeftColumnWidth()
0x285aa  ldc.i4.0
0x285ab  ble.un   loc_28708
0x285b0  ldarg.0
0x285b1  ldloc.0
0x285b2  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderNonDataHeaderColumn(class [mscorlib]System.IO.TextWriter writer)
0x285b7  ldloc.2
0x285b8  ldc.i4   0x43D
0x285bd  bgt.s    loc_285D4
0x285bf  ldloc.2
0x285c0  ldc.i4   0x43B
0x285c5  beq.s    loc_285E7
0x285c7  ldloc.2
0x285c8  ldc.i4   0x43D
0x285cd  beq.s    loc_285E7
0x285cf  br       loc_286C8
0x285d4  ldloc.2
0x285d5  ldc.i4   0x441
0x285da  beq.s    loc_285E7
0x285dc  ldloc.2
0x285dd  ldc.i4   0x443
0x285e2  bne.un   loc_286C8
0x285e7  ldarg.0
0x285e8  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x285ed  ldstr    aViewid// "viewid"
0x285f2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x285f7  brfalse.s loc_2863D
0x285f9  ldarg.0
0x285fa  ldarg.0
0x285fb  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x28600  ldstr    aViewid// "viewid"
0x28605  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2860a  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::IsInlineEditSubGridView(string viewId)
0x2860f  brfalse.s loc_2863D
0x28611  ldarg.0
0x28612  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x28617  ldstr    aGridtype// "GridType"
0x2861c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x28621  ldstr    aSubgrid// "SubGrid"
0x28626  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2862b  brfalse.s loc_2863D
0x2862d  ldloc.0
0x2862e  ldstr    aColWidth22// "<col width=\"22\">"
0x28633  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x28638  br       loc_28708
0x2863d  ldarg.0
0x2863e  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x28643  ldstr    aViewid// "viewid"
0x28648  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2864d  brfalse.s loc_286BB
0x2864f  ldarg.0
0x28650  ldarg.0
0x28651  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x28656  ldstr    aViewid// "viewid"
0x2865b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x28660  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::IsInlineEditSubGridView(string viewId)
0x28665  brtrue.s loc_286BB
0x28667  ldarg.0
0x28668  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x2866d  ldstr    aGridtype// "GridType"
0x28672  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x28677  ldstr    aSubgrid// "SubGrid"
0x2867c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28681  brfalse.s loc_286BB
0x28683  ldarg.0
0x28684  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::get_Parent()
0x28689  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x2868e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x28693  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x28698  ldstr    aIsturboform// "isTurboForm"
0x2869d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x286a2  ldstr    aTrue// "true"
0x286a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x286ac  brfalse.s loc_286BB
0x286ae  ldloc.0
0x286af  ldstr    aColWidth60// "<col width=\"60\">"
0x286b4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x286b9  br.s     loc_28708
0x286bb  ldloc.0
0x286bc  ldstr    aColWidth22// "<col width=\"22\">"
0x286c1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x286c6  br.s     loc_28708
0x286c8  ldarg.0
0x286c9  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x286ce  ldstr    aGridtype// "GridType"
0x286d3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x286d8  ldstr    aSubgrid// "SubGrid"
0x286dd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x286e2  brfalse.s loc_286FD
0x286e4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x286e9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x286ee  brtrue.s loc_286FD
0x286f0  ldloc.0
0x286f1  ldstr    aColWidth18// "<col width=\"18\">"
0x286f6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x286fb  br.s     loc_28708
0x286fd  ldloc.0
0x286fe  ldstr    aColWidth2// "<col width=\"2\">"
0x28703  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x28708  ldarg.0
0x28709  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Columns()
0x2870e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x28713  stloc.3
0x28714  br.s     loc_2877B
0x28716  ldloc.3
0x28717  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2871c  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column
0x28721  stloc.s  4
0x28723  ldloc.s  4
0x28725  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0x2872a  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_IsHidden()
0x2872f  brtrue.s loc_2877B
0x28731  ldarg.0
0x28732  ldloc.s  4
0x28734  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0x28739  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::ShouldHideColumnUnderFCB(string fieldName)
0x2873e  brtrue.s loc_2877B
0x28740  ldloc.0
0x28741  ldstr    aColClassMsCrmL// "<col class=\"ms-crm-List-DataColumnHead"...
0x28746  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2874b  ldloc.0
0x2874c  ldloc.s  4
0x2874e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0x28753  callvirt instance unsigned int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_Width()
0x28758  stloc.s  5
0x2875a  ldloca.s 5
0x2875c  ldstr    aD_1// "D"
0x28761  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28766  call     instance string [mscorlib]System.UInt32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2876b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x28770  ldloc.0
0x28771  ldstr    aColWidth2_0// "\"><col width=\"2\">"
0x28776  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2877b  ldloc.3
0x2877c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x28781  brtrue.s loc_28716
0x28783  leave.s  loc_28799
0x28785  ldloc.3
0x28786  isinst   [mscorlib]System.IDisposable
0x2878b  stloc.s  6
0x2878d  ldloc.s  6
0x2878f  brfalse.s loc_28798
0x28791  ldloc.s  6
0x28793  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28798  endfinally
0x28799  ldarg.0
0x2879a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Columns()
0x2879f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x287a4  stloc.3
0x287a5  br.s     loc_287DC
0x287a7  ldloc.3
0x287a8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x287ad  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column
0x287b2  stloc.s  7
0x287b4  ldloc.s  7
0x287b6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0x287bb  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_IsHidden()
0x287c0  brtrue.s loc_287D1
0x287c2  ldarg.0
0x287c3  ldloc.s  7
0x287c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0x287ca  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::ShouldHideColumnUnderFCB(string fieldName)
0x287cf  brfalse.s loc_287DC
0x287d1  ldloc.0
0x287d2  ldstr    aColWidth0Style// "<col width=\"0\" style=\"display:none;"...
0x287d7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x287dc  ldloc.3
0x287dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x287e2  brtrue.s loc_287A7
0x287e4  leave.s  loc_287FA
0x287e6  ldloc.3
0x287e7  isinst   [mscorlib]System.IDisposable
0x287ec  stloc.s  6
0x287ee  ldloc.s  6
0x287f0  brfalse.s loc_287F9
0x287f2  ldloc.s  6
0x287f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x287f9  endfinally
0x287fa  ldarg.0
0x287fb  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_EnableRefresh()
0x28800  brtrue.s loc_2880A
0x28802  ldarg.0
0x28803  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::CanFilterEnable()
0x28808  brfalse.s loc_28815
0x2880a  ldloc.0
0x2880b  ldstr    aColWidth60// "<col width=\"60\">"
0x28810  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x28815  ldloc.0
0x28816  ldstr    aCol// "<col>"
0x2881b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x28820  ldloc.0
0x28821  ldstr    aColgroup_0// "</colgroup>"
0x28826  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2882b  ldloc.0
0x2882c  ldstr    aTrStyleHeight0// "<tr style=\"height: {0}px\">"
0x28831  ldarg.0
0x28832  callvirt instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Default_Grid_Header_Height()
0x28837  ldc.i4.2
0x28838  sub
0x28839  box      [mscorlib]System.Int32
0x2883e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x28843  ldarg.0
0x28844  call     instance unsigned int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_LeftColumnWidth()
0x28849  ldc.i4.0
0x2884a  ble.un.s loc_28871
0x2884c  ldarg.0
0x2884d  ldarg.1
0x2884e  ldloc.0
0x2884f  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderNonDataHeaderCell(class [System.Web]System.Web.UI.HtmlTextWriter output, class [mscorlib]System.IO.TextWriter writer)
  ... truncated ...
```
