# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderStatusBarInnerHtml

- ea: `0x29980`
- end: `0x2a13a`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderStatusBarInnerHtml`
- size: `1978`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x29850`

## callees

- `0x1a0a0`
- `0x1a0d0`
- `0x1a350`
- `0x1a390`
- `0x224d0`
- `0x26dd0`
- `0x26df0`
- `0x26e10`
- `0x26e30`
- `0x26e50`
- `0x26e70`
- `0x26e90`
- `0x26eb0`
- `0x26fd0`
- `0x27220`
- `0x272d0`
- `0x27370`
- `0x273f0`
- `0x27430`
- `0x281e0`
- `0x29930`
- `0x29950`
- `0x29980`
- `0x2a140`

## string_xrefs

- `0x29d5b`: ` tempToolTip="`
- `0x29e93`: ` tempToolTip="`
- `0x2a055`: ` tempToolTip="`

## pseudocode

```c

```

## disassembly

```asm
0x29980  ldarg.1
0x29981  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x29986  stloc.0
0x29987  ldstr    asc_3280A// ""
0x2998c  stloc.1
0x2998d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29992  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29997  brfalse.s loc_299B7
0x29999  ldloc.0
0x2999a  ldstr    aTableCellspaci_3// "<table cellSpacing=0 cellPadding=0 id="...
0x2999f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x299a4  ldarg.0
0x299a5  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_GridStatusBarCssClass()
0x299aa  ldstr    aMsCrmListStatu_0// " ms-crm-List-StatusBar-Height"
0x299af  call     string [mscorlib]System.String::Concat(string, string)
0x299b4  stloc.1
0x299b5  br.s     loc_299C9
0x299b7  ldloc.0
0x299b8  ldstr    aTableCellspaci_4// "<table cellSpacing=0 cellPadding=0 id="...
0x299bd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x299c2  ldarg.0
0x299c3  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_GridStatusBarCssClass()
0x299c8  stloc.1
0x299c9  ldstr    aClass_1// "class"
0x299ce  ldloc.1
0x299cf  ldarg.1
0x299d0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x299d5  ldloc.0
0x299d6  ldstr    aTr_4// "><tr>"
0x299db  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x299e0  ldarg.0
0x299e1  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_MaximumSelectableItems()
0x299e6  ldc.i4.0
0x299e7  bgt.s    loc_29A0D
0x299e9  ldarg.0
0x299ea  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_MaximumSelectableItems()
0x299ef  ldc.i4.m1
0x299f0  beq.s    loc_29A0D
0x299f2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x299f7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x299fc  brfalse  loc_29C2C
0x29a01  ldarg.0
0x29a02  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_MaximumSelectableItems()
0x29a07  ldc.i4.m1
0x29a08  blt      loc_29C2C
0x29a0d  ldarg.0
0x29a0e  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_StatusMessageMask()
0x29a13  brfalse.s loc_29A23
0x29a15  ldarg.0
0x29a16  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_StatusMessageMask()
0x29a1b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x29a20  ldc.i4.0
0x29a21  bgt.s    loc_29A3D
0x29a23  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29a28  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29a2d  brfalse  loc_29C1C
0x29a32  ldarg.0
0x29a33  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_MaximumSelectableItems()
0x29a38  brtrue   loc_29C1C
0x29a3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29a42  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29a47  brfalse.s loc_29A56
0x29a49  ldloc.0
0x29a4a  ldstr    aTdClassMsCrmLi// "<td CLASS=\"ms-crm-List-StatusBar-Label"...
0x29a4f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29a54  br.s     loc_29A61
0x29a56  ldloc.0
0x29a57  ldstr    aTdNowrapClassM_0// "<td nowrap CLASS=\"ms-crm-List-StatusBa"...
0x29a5c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29a61  ldarg.0
0x29a62  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x29a67  ldloc.0
0x29a68  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x29a6d  ldloc.0
0x29a6e  ldstr    aRecordselectin// "_RecordSelectInfo\">"
0x29a73  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29a78  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29a7d  ldstr    aSpanId0Firstit// "<span id=\"{0}_FirstItem\">0</span>"
0x29a82  ldc.i4.1
0x29a83  newarr   [mscorlib]System.Object
0x29a88  dup
0x29a89  ldc.i4.0
0x29a8a  ldarg.0
0x29a8b  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x29a90  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x29a95  stelem.ref
0x29a96  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29a9b  stloc.2
0x29a9c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29aa1  ldstr    aSpanId0Lastite// "<span id=\"{0}_LastItem\">0</span>"
0x29aa6  ldc.i4.1
0x29aa7  newarr   [mscorlib]System.Object
0x29aac  dup
0x29aad  ldc.i4.0
0x29aae  ldarg.0
0x29aaf  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x29ab4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x29ab9  stelem.ref
0x29aba  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29abf  stloc.3
0x29ac0  ldstr    asc_3280A// ""
0x29ac5  stloc.s  4
0x29ac7  ldstr    asc_3280A// ""
0x29acc  stloc.s  5
0x29ace  ldstr    asc_3280A// ""
0x29ad3  stloc.s  6
0x29ad5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29ada  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29adf  brtrue.s loc_29B3B
0x29ae1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29ae6  ldstr    aSpanId0Itemsse// "<span id=\"{0}_ItemsSelected\">0</span>"
0x29aeb  ldc.i4.1
0x29aec  newarr   [mscorlib]System.Object
0x29af1  dup
0x29af2  ldc.i4.0
0x29af3  ldarg.0
0x29af4  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x29af9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x29afe  stelem.ref
0x29aff  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29b04  stloc.s  4
0x29b06  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29b0b  ldarg.0
0x29b0c  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_ItemsSelectedMask()
0x29b11  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x29b16  ldc.i4.2
0x29b17  newarr   [mscorlib]System.Object
0x29b1c  dup
0x29b1d  ldc.i4.0
0x29b1e  ldarg.0
0x29b1f  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TotalCountSpaceMask()
0x29b24  stelem.ref
0x29b25  dup
0x29b26  ldc.i4.1
0x29b27  ldloc.s  4
0x29b29  stelem.ref
0x29b2a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29b2f  stloc.s  5
0x29b31  ldarg.0
0x29b32  ldloc.s  5
0x29b34  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::GetItemSelectedInfo(string itemsSelectedMask)
0x29b39  stloc.s  6
0x29b3b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29b40  ldstr    aSpanId0Itemsto// "<span id=\"{0}_ItemsTotal\">0</span>"
0x29b45  ldc.i4.1
0x29b46  newarr   [mscorlib]System.Object
0x29b4b  dup
0x29b4c  ldc.i4.0
0x29b4d  ldarg.0
0x29b4e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x29b53  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x29b58  stelem.ref
0x29b59  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29b5e  stloc.s  7
0x29b60  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29b65  ldarg.0
0x29b66  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TotalCountMask()
0x29b6b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x29b70  ldc.i4.2
0x29b71  newarr   [mscorlib]System.Object
0x29b76  dup
0x29b77  ldc.i4.0
0x29b78  ldarg.0
0x29b79  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TotalCountSpaceMask()
0x29b7e  stelem.ref
0x29b7f  dup
0x29b80  ldc.i4.1
0x29b81  ldloc.s  7
0x29b83  stelem.ref
0x29b84  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29b89  stloc.s  8
0x29b8b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29b90  ldstr    aSpanId0Totalco// "<span id=\"{0}_TotalCountInfo\">{1}</sp"...
0x29b95  ldc.i4.2
0x29b96  newarr   [mscorlib]System.Object
0x29b9b  dup
0x29b9c  ldc.i4.0
0x29b9d  ldarg.0
0x29b9e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x29ba3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x29ba8  stelem.ref
0x29ba9  dup
0x29baa  ldc.i4.1
0x29bab  ldloc.s  8
0x29bad  stelem.ref
0x29bae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29bb3  stloc.s  9
0x29bb5  ldarg.0
0x29bb6  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_StatusMessageMask()
0x29bbb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x29bc0  stloc.s  0xA
0x29bc2  ldloc.0
0x29bc3  ldloc.s  0xA
0x29bc5  ldc.i4.4
0x29bc6  newarr   [mscorlib]System.Object
0x29bcb  dup
0x29bcc  ldc.i4.0
0x29bcd  ldloc.2
0x29bce  stelem.ref
0x29bcf  dup
0x29bd0  ldc.i4.1
0x29bd1  ldloc.3
0x29bd2  stelem.ref
0x29bd3  dup
0x29bd4  ldc.i4.2
0x29bd5  ldloc.s  9
0x29bd7  stelem.ref
0x29bd8  dup
0x29bd9  ldc.i4.3
0x29bda  ldloc.s  6
0x29bdc  stelem.ref
0x29bdd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object[])
0x29be2  ldloc.0
0x29be3  ldstr    aSpanId// "<span id=\""
0x29be8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29bed  ldarg.0
0x29bee  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x29bf3  ldloc.0
0x29bf4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x29bf9  ldloc.0
0x29bfa  ldstr    aRecordselecten// "_RecordSelectEndMarker\""
0x29bff  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29c04  ldloc.0
0x29c05  ldstr    aStyleVisibilit// " style=\"VISIBILITY: hidden;\">M</span>"
0x29c0a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29c0f  ldloc.0
0x29c10  ldstr    aTd// "</td>"
0x29c15  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29c1a  br.s     loc_29C2C
0x29c1c  ldstr    aStatusmessagem// "StatusMessageMask"
0x29c21  ldstr    aTheStatusmessa// "The StatusMessageMask can not be NULL w"...
0x29c26  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x29c2b  throw
0x29c2c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29c31  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29c36  brfalse.s loc_29C3F
0x29c38  ldarg.0
0x29c39  ldarg.1
0x29c3a  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFooterRow(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x29c3f  ldarg.0
0x29c40  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_EnablePaging()
0x29c45  brfalse  loc_2A12E
0x29c4a  ldarg.0
0x29c4b  callvirt instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RetrieveHorizontalSpace()
0x29c50  stloc.s  0xF
0x29c52  ldloca.s 0xF
0x29c54  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29c59  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x29c5e  stloc.s  0xB
0x29c60  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29c65  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29c6a  brfalse.s loc_29C79
0x29c6c  ldloc.0
0x29c6d  ldstr    aTdNowrapWidthA// "<td nowrap width=\"auto\" style=\"displ"...
0x29c72  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29c77  br.s     loc_29C84
0x29c79  ldloc.0
0x29c7a  ldstr    aTdNowrapId// "<td nowrap id=\""
0x29c7f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29c84  ldarg.0
0x29c85  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x29c8a  ldloc.0
0x29c8b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x29c90  ldloc.0
0x29c91  ldstr    aPageinfo// "_PageInfo\""
0x29c96  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x29c9b  ldstr    aClass_1// "class"
0x29ca0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29ca5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29caa  brtrue.s loc_29CB4
0x29cac  ldarg.0
0x29cad  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_GridPagingCssClass()
0x29cb2  br.s     loc_29CC4
0x29cb4  ldarg.0
0x29cb5  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_GridPagingCssClass()
0x29cba  ldstr    aMsCrmListStatu_1// " ms-crm-List-StatusBar-Label-Padding"
0x29cbf  call     string [mscorlib]System.String::Concat(string, string)
0x29cc4  ldarg.1
0x29cc5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x29cca  ldloc.0
0x29ccb  ldc.i4.s 0x3E
0x29ccd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x29cd2  ldloc.0
0x29cd3  ldc.i4.5
0x29cd4  newarr   [mscorlib]System.String
0x29cd9  dup
0x29cda  ldc.i4.0
0x29cdb  ldstr    aA_3// "<a "
0x29ce0  stelem.ref
0x29ce1  dup
0x29ce2  ldc.i4.1
0x29ce3  ldarg.0
0x29ce4  ldarg.0
0x29ce5  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_FastRewindButtonToolTip()
0x29cea  call     instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::TitleTag(string tooltip)
0x29cef  stelem.ref
0x29cf0  dup
0x29cf1  ldc.i4.2
0x29cf2  ldstr    aOnclickReturnF// " onclick=\"return false;\" href=\"#\" t"...
0x29cf7  stelem.ref
  ... truncated ...
```
