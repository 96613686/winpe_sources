# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFilterButton

- ea: `0x27be0`
- end: `0x27d25`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFilterButton`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x27d30`

## callees

- `0x1a3b0`
- `0x1a400`
- `0x1a410`
- `0x24210`
- `0x26f10`
- `0x26fd0`
- `0x27b70`
- `0x27be0`

## string_xrefs

- `0x27c10`: `"  id="filterButtonLink"  tabindex="`

## pseudocode

```c

```

## disassembly

```asm
0x27be0  ldarg.0
0x27be1  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::CanFilterEnable()
0x27be6  brfalse  loc_27D24
0x27beb  ldarg.1
0x27bec  ldstr    aDivIdFilterbut// "<div id=\"filterButton\" class=\"ms-crm"...
0x27bf1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27bf6  ldarg.1
0x27bf7  ldc.i4.5
0x27bf8  newarr   [mscorlib]System.String
0x27bfd  dup
0x27bfe  ldc.i4.0
0x27bff  ldstr    aAHrefTitle// "<a href=\"#\" title=\""
0x27c04  stelem.ref
0x27c05  dup
0x27c06  ldc.i4.1
0x27c07  ldarg.0
0x27c08  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_FilterGridToolTip()
0x27c0d  stelem.ref
0x27c0e  dup
0x27c0f  ldc.i4.2
0x27c10  ldstr    aIdFilterbutton// "\"  id=\"filterButtonLink\"  tabindex="...
0x27c15  stelem.ref
0x27c16  dup
0x27c17  ldc.i4.3
0x27c18  ldarg.0
0x27c19  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TabIndex()
0x27c1e  stloc.1
0x27c1f  ldloca.s 1
0x27c21  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27c26  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x27c2b  stelem.ref
0x27c2c  dup
0x27c2d  ldc.i4.4
0x27c2e  ldstr    asc_42682// "\">"
0x27c33  stelem.ref
0x27c34  call     string [mscorlib]System.String::Concat(string[])
0x27c39  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27c3e  ldarg.0
0x27c3f  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_FilterGridToolTip()
0x27c44  brfalse.s loc_27C54
0x27c46  ldarg.0
0x27c47  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_FilterGridToolTip()
0x27c4c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x27c51  ldc.i4.0
0x27c52  bgt.s    loc_27C5B
0x27c54  ldsfld   string [mscorlib]System.String::Empty
0x27c59  br.s     loc_27C61
0x27c5b  ldarg.0
0x27c5c  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_FilterGridToolTip()
0x27c61  stloc.0
0x27c62  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x27c67  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x27c6c  brfalse.s loc_27CE9
0x27c6e  ldstr    aImgsImagestrip// "/_imgs/imagestrips/transparent_spacer.g"...
0x27c73  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27c78  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27c7d  dup
0x27c7e  ldc.i4.0
0x27c7f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseVersionStamp(bool)
0x27c84  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri source)
0x27c89  stloc.2
0x27c8a  ldloc.2
0x27c8b  ldstr    aStyle_0// "style"
0x27c90  ldstr    aCursorPointerM// "cursor:pointer; margin-top:2px; margin-"...
0x27c95  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x27c9a  ldloc.2
0x27c9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27ca0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27ca5  brtrue.s loc_27CAE
0x27ca7  ldstr    aMsCrmImagestri_1// "ms-crm-ImageStrip-grid_filter"
0x27cac  br.s     loc_27CB3
0x27cae  ldstr    aMsCrmImagestri_2// "ms-crm-ImageStrip-grid_visualrefresh_fi"...
0x27cb3  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x27cb8  ldloc.2
0x27cb9  ldstr    aFilterbuttonim// "filterButtonImage"
0x27cbe  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x27cc3  ldloc.2
0x27cc4  ldstr    aAlt// "alt"
0x27cc9  ldloc.0
0x27cca  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x27ccf  ldloc.2
0x27cd0  ldstr    aTitle_2// "title"
0x27cd5  ldloc.0
0x27cd6  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x27cdb  ldarg.1
0x27cdc  ldloc.2
0x27cdd  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_OuterHtml()
0x27ce2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27ce7  br.s     loc_27D19
0x27ce9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27cee  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27cf3  brfalse.s loc_27D08
0x27cf5  ldarg.1
0x27cf6  ldstr    aImgSrcImgsGrid// "<img src=\"/_imgs/grid/grid_visualrefre"...
0x27cfb  ldloc.0
0x27cfc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncodeForFormatString(string)
0x27d01  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27d06  br.s     loc_27D19
0x27d08  ldarg.1
0x27d09  ldstr    aImgSrcImgsGrid_0// "<img src=\"/_imgs/grid/grid_filter.png"...
0x27d0e  ldloc.0
0x27d0f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncodeForFormatString(string)
0x27d14  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27d19  ldarg.1
0x27d1a  ldstr    aADiv// "</a></div>"
0x27d1f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27d24  ret
```
