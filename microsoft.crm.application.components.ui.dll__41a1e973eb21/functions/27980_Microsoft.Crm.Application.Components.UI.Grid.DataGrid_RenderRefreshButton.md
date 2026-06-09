# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderRefreshButton

- ea: `0x27980`
- end: `0x27b64`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderRefreshButton`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x27d30`

## callees

- `0x1a3b0`
- `0x1a3f0`
- `0x1a400`
- `0x1a410`
- `0x24210`
- `0x26ef0`
- `0x26fd0`
- `0x27160`
- `0x27980`
- `0x29950`

## string_xrefs

- `0x279c2`: ` href="#" id="refreshButtonLink" tabindex="`
- `0x27a12`: ` href="#" id="refreshButtonLink" tabindex="`

## pseudocode

```c

```

## disassembly

```asm
0x27980  ldarg.0
0x27981  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_EnableRefresh()
0x27986  brfalse  loc_27B63
0x2798b  ldarg.1
0x2798c  ldstr    aDivIdRefreshbu// "<div id=\"refreshButton\" class=\"ms-cr"...
0x27991  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27996  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2799b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x279a0  brfalse.s loc_279F2
0x279a2  ldarg.1
0x279a3  ldc.i4.5
0x279a4  newarr   [mscorlib]System.String
0x279a9  dup
0x279aa  ldc.i4.0
0x279ab  ldstr    aA_3// "<a "
0x279b0  stelem.ref
0x279b1  dup
0x279b2  ldc.i4.1
0x279b3  ldarg.0
0x279b4  ldarg.0
0x279b5  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RefreshGridToolTip()
0x279ba  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::TitleTag(string tooltip)
0x279bf  stelem.ref
0x279c0  dup
0x279c1  ldc.i4.2
0x279c2  ldstr    aHrefIdRefreshb// " href=\"#\" id=\"refreshButtonLink\" ta"...
0x279c7  stelem.ref
0x279c8  dup
0x279c9  ldc.i4.3
0x279ca  ldarg.0
0x279cb  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TabIndex()
0x279d0  stloc.1
0x279d1  ldloca.s 1
0x279d3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x279d8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x279dd  stelem.ref
0x279de  dup
0x279df  ldc.i4.4
0x279e0  ldstr    aSpan_8// "\"><span>"
0x279e5  stelem.ref
0x279e6  call     string [mscorlib]System.String::Concat(string[])
0x279eb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x279f0  br.s     loc_27A40
0x279f2  ldarg.1
0x279f3  ldc.i4.5
0x279f4  newarr   [mscorlib]System.String
0x279f9  dup
0x279fa  ldc.i4.0
0x279fb  ldstr    aA_3// "<a "
0x27a00  stelem.ref
0x27a01  dup
0x27a02  ldc.i4.1
0x27a03  ldarg.0
0x27a04  ldarg.0
0x27a05  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RefreshGridToolTip()
0x27a0a  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::TitleTag(string tooltip)
0x27a0f  stelem.ref
0x27a10  dup
0x27a11  ldc.i4.2
0x27a12  ldstr    aHrefIdRefreshb// " href=\"#\" id=\"refreshButtonLink\" ta"...
0x27a17  stelem.ref
0x27a18  dup
0x27a19  ldc.i4.3
0x27a1a  ldarg.0
0x27a1b  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TabIndex()
0x27a20  stloc.1
0x27a21  ldloca.s 1
0x27a23  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27a28  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x27a2d  stelem.ref
0x27a2e  dup
0x27a2f  ldc.i4.4
0x27a30  ldstr    asc_42682// "\">"
0x27a35  stelem.ref
0x27a36  call     string [mscorlib]System.String::Concat(string[])
0x27a3b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27a40  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27a45  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27a4a  brtrue.s loc_27A53
0x27a4c  ldstr    aImgsGridGridRe// "/_imgs/grid/grid_refresh.gif"
0x27a51  br.s     loc_27A58
0x27a53  ldstr    aImgsGridGridVi// "/_imgs/grid/grid_visualrefresh_refresh."...
0x27a58  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27a5d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27a62  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri source)
0x27a67  stloc.0
0x27a68  ldloc.0
0x27a69  ldstr    aStyle_0// "style"
0x27a6e  ldstr    aCursorPointer// "cursor:pointer"
0x27a73  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x27a78  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x27a7d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x27a82  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSafari(class [System.Web]System.Web.HttpRequest)
0x27a87  brfalse.s loc_27AB8
0x27a89  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x27a8e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x27a93  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsGoogleChrome(class [System.Web]System.Web.HttpRequest)
0x27a98  brtrue.s loc_27AB8
0x27a9a  ldloc.0
0x27a9b  ldstr    aTabindex_0// "tabIndex"
0x27aa0  ldarg.0
0x27aa1  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TabIndex()
0x27aa6  stloc.1
0x27aa7  ldloca.s 1
0x27aa9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27aae  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x27ab3  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x27ab8  ldarg.0
0x27ab9  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RefreshGridToolTip()
0x27abe  brfalse.s loc_27AF2
0x27ac0  ldarg.0
0x27ac1  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RefreshGridToolTip()
0x27ac6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x27acb  ldc.i4.0
0x27acc  ble.s    loc_27AF2
0x27ace  ldloc.0
0x27acf  ldstr    aAlt// "alt"
0x27ad4  ldarg.0
0x27ad5  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RefreshGridToolTip()
0x27ada  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x27adf  ldloc.0
0x27ae0  ldstr    aTitle_2// "title"
0x27ae5  ldarg.0
0x27ae6  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RefreshGridToolTip()
0x27aeb  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x27af0  br.s     loc_27B12
0x27af2  ldloc.0
0x27af3  ldstr    aAlt// "alt"
0x27af8  ldsfld   string [mscorlib]System.String::Empty
0x27afd  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x27b02  ldloc.0
0x27b03  ldstr    aTitle_2// "title"
0x27b08  ldsfld   string [mscorlib]System.String::Empty
0x27b0d  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x27b12  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27b17  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27b1c  brtrue.s loc_27B34
0x27b1e  ldloc.0
0x27b1f  dup
0x27b20  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_CssClass()
0x27b25  ldstr    aMsCrmGridrefre// " ms-crm-GridRefreshImage"
0x27b2a  call     string [mscorlib]System.String::Concat(string, string)
0x27b2f  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x27b34  ldarg.1
0x27b35  ldloc.0
0x27b36  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_OuterHtml()
0x27b3b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27b40  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27b45  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27b4a  brfalse.s loc_27B58
0x27b4c  ldarg.1
0x27b4d  ldstr    aSpanADiv// "</span></a></div>"
0x27b52  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27b57  ret
0x27b58  ldarg.1
0x27b59  ldstr    aADiv// "</a></div>"
0x27b5e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27b63  ret
```
