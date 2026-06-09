# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderNonDataHeaderCell

- ea: `0x29330`
- end: `0x294d6`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderNonDataHeaderCell`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x284a0`

## callees

- `0x154b0`
- `0x155d0`
- `0x1a0a0`
- `0x1a0d0`
- `0x1a350`
- `0x1a390`
- `0x24210`
- `0x242d0`
- `0x26da0`
- `0x26db0`
- `0x26fd0`
- `0x272f0`
- `0x27370`
- `0x276e0`
- `0x27740`
- `0x29330`

## pseudocode

```c

```

## disassembly

```asm
0x29330  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29335  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2933a  brfalse.s loc_29373
0x2933c  ldarg.2
0x2933d  ldstr    aTdStyleHeight0// "<td style=\"height: {0}px; padding: 0px"...
0x29342  ldarg.0
0x29343  callvirt instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Default_Grid_Header_Height()
0x29348  ldc.i4.2
0x29349  sub
0x2934a  box      [mscorlib]System.Int32
0x2934f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x29354  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x29359  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x2935e  brtrue.s loc_29367
0x29360  ldstr    aPaddingLeft12p// " padding-left:12px;"
0x29365  br.s     loc_2936C
0x29367  ldstr    aPaddingRight12// " padding-right:12px;"
0x2936c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x29371  br.s     loc_2938B
0x29373  ldarg.2
0x29374  ldstr    aTdStyleHeight0_0// "<td style=\"height: {0}px; text-align: "...
0x29379  ldarg.0
0x2937a  callvirt instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Default_Grid_Header_Height()
0x2937f  ldc.i4.2
0x29380  sub
0x29381  box      [mscorlib]System.Int32
0x29386  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x2938b  ldarg.0
0x2938c  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_MaximumSelectableItems()
0x29391  conv.i8
0x29392  ldarg.0
0x29393  call     instance unsigned int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RecordsPerPage()
0x29398  conv.u8
0x29399  blt.s    loc_293A3
0x2939b  ldarg.0
0x2939c  call     instance unsigned int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RecordsPerPage()
0x293a1  brtrue.s loc_293AF
0x293a3  ldarg.0
0x293a4  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_MaximumSelectableItems()
0x293a9  ldc.i4.m1
0x293aa  bne.un   loc_294BF
0x293af  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBox::.ctor()
0x293b4  stloc.3
0x293b5  ldloc.3
0x293b6  ldstr    aMsCrmHeaderche// "ms-crm-HeaderCheckBox"
0x293bb  ldarg.0
0x293bc  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_CssSuffix()
0x293c1  call     string [mscorlib]System.String::Concat(string, string)
0x293c6  callvirt instance void Microsoft.Crm.Application.Components.UI.CheckBox::set_ClassName(string value)
0x293cb  ldloc.3
0x293cc  ldarg.0
0x293cd  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TabIndex()
0x293d2  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::set_TabIndex(int32 value)
0x293d7  ldloc.3
0x293d8  ldstr    aChkall// "chkAll"
0x293dd  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x293e2  ldarg.0
0x293e3  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_SelectAllItemsToolTip()
0x293e8  brfalse.s loc_29409
0x293ea  ldarg.0
0x293eb  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_SelectAllItemsToolTip()
0x293f0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x293f5  ldc.i4.0
0x293f6  ble.s    loc_29409
0x293f8  ldloc.3
0x293f9  ldstr    aTitle_2// "title"
0x293fe  ldarg.0
0x293ff  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_SelectAllItemsToolTip()
0x29404  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x29409  ldloc.3
0x2940a  ldarg.1
0x2940b  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x29410  leave.s  loc_2941C
0x29412  ldloc.3
0x29413  brfalse.s loc_2941B
0x29415  ldloc.3
0x29416  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2941b  endfinally
0x2941c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29421  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29426  brtrue.s loc_2942F
0x29428  ldstr    aImgsGridCheckb// "/_imgs/grid/checkbox.png"
0x2942d  br.s     loc_29434
0x2942f  ldstr    aImgsGridCheckb_0// "/_imgs/grid/checkbox_visualrefresh_ligh"...
0x29434  stloc.0
0x29435  call     class Microsoft.Crm.Application.Components.UI.ImageStrip Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x2943a  ldloc.0
0x2943b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29440  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29445  callvirt instance class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri imagePath)
0x2944a  stloc.1
0x2944b  ldarg.0
0x2944c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x29451  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x29456  ldstr    aGridbodytableC// "_gridBodyTable_checkBox_Image_All"
0x2945b  call     string [mscorlib]System.String::Concat(string, string)
0x29460  stloc.2
0x29461  ldarg.2
0x29462  ldstr    aImgSrc0RoleBut// "<img src=\"{0}\" role=\"button\" class="...
0x29467  ldc.i4.5
0x29468  newarr   [mscorlib]System.Object
0x2946d  dup
0x2946e  ldc.i4.0
0x2946f  ldloc.1
0x29470  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x29475  callvirt instance string [mscorlib]System.Object::ToString()
0x2947a  stelem.ref
0x2947b  dup
0x2947c  ldc.i4.1
0x2947d  ldarg.0
0x2947e  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_HeaderCheckBoxImageClass()
0x29483  ldstr    asc_4C79A// " "
0x29488  ldloc.1
0x29489  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x2948e  call     string [mscorlib]System.String::Concat(string, string, string)
0x29493  stelem.ref
0x29494  dup
0x29495  ldc.i4.2
0x29496  ldloc.2
0x29497  stelem.ref
0x29498  dup
0x29499  ldc.i4.3
0x2949a  ldarg.0
0x2949b  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_SelectAllItemsToolTip()
0x294a0  stelem.ref
0x294a1  dup
0x294a2  ldc.i4.4
0x294a3  ldarg.0
0x294a4  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TabIndex()
0x294a9  stloc.s  4
0x294ab  ldloca.s 4
0x294ad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x294b2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x294b7  stelem.ref
0x294b8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object[])
0x294bd  br.s     loc_294CA
0x294bf  ldarg.2
0x294c0  ldstr    aNbsp// "&nbsp;"
0x294c5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x294ca  ldarg.2
0x294cb  ldstr    aTd// "</td>"
0x294d0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x294d5  ret
```
