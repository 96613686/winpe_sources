# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderInnerHtml

- ea: `0x27d60`
- end: `0x27f5d`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderInnerHtml`
- size: `509`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x276b0`
- `0x27750`

## callees

- `0x27120`
- `0x271d0`
- `0x27450`
- `0x276e0`
- `0x27710`
- `0x27740`
- `0x27d60`
- `0x27f60`
- `0x28060`
- `0x28350`
- `0x28450`
- `0x284a0`
- `0x29850`

## pseudocode

```c

```

## disassembly

```asm
0x27d60  ldarg.1
0x27d61  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x27d66  stloc.0
0x27d67  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x27d6c  stloc.1
0x27d6d  ldloc.1
0x27d6e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x27d73  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x27d78  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x27d7d  stloc.2
0x27d7e  ldarg.0
0x27d7f  ldarg.0
0x27d80  ldloc.2
0x27d81  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderData(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x27d86  ldc.i4.0
0x27d87  ceq
0x27d89  stfld    bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::errorOccured
0x27d8e  ldloc.0
0x27d8f  ldstr    aDivClass0Style// "<div class=\"{0}\" style=\"position:rel"...
0x27d94  ldarg.0
0x27d95  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_EnableColumnHeader()
0x27d9a  brtrue.s loc_27DAB
0x27d9c  ldarg.0
0x27d9d  ldfld    bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::errorOccured
0x27da2  brtrue.s loc_27DAB
0x27da4  ldstr    aMsCrmListareae// "ms-crm-ListAreaEx"
0x27da9  br.s     loc_27DB0
0x27dab  ldstr    aMsCrmListarea// "ms-crm-ListArea"
0x27db0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27db5  ldc.i4.0
0x27db6  stloc.3
0x27db7  ldarg.0
0x27db8  ldfld    bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::errorOccured
0x27dbd  brtrue.s loc_27DCF
0x27dbf  ldarg.0
0x27dc0  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::CanRenderStatusBar()
0x27dc5  brfalse.s loc_27DCF
0x27dc7  ldarg.0
0x27dc8  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_ShowStatusBar()
0x27dcd  brtrue.s loc_27DD2
0x27dcf  ldc.i4.0
0x27dd0  br.s     loc_27DD8
0x27dd2  ldarg.0
0x27dd3  call     instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Default_Grid_Status_Height()
0x27dd8  stloc.s  4
0x27dda  ldarg.0
0x27ddb  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_EnableColumnHeader()
0x27de0  brfalse  loc_27E78
0x27de5  ldarg.0
0x27de6  ldfld    bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::errorOccured
0x27deb  brtrue   loc_27E78
0x27df0  ldarg.0
0x27df1  callvirt instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Default_Grid_Header_Height()
0x27df6  stloc.s  6
0x27df8  ldarg.0
0x27df9  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_CssSuffix()
0x27dfe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x27e03  brtrue.s loc_27E2D
0x27e05  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27e0a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27e0f  brtrue.s loc_27E15
0x27e11  ldloc.s  6
0x27e13  br.s     loc_27E17
0x27e15  ldc.i4.s 0x1E
0x27e17  stloc.s  6
0x27e19  ldloc.0
0x27e1a  ldstr    aDivClassMsCrmG_2// "<div class=\"ms-crm-grid-BodyContainer"...
0x27e1f  ldloc.s  6
0x27e21  box      [mscorlib]System.Int32
0x27e26  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27e2b  br.s     loc_27E3F
0x27e2d  ldloc.0
0x27e2e  ldstr    aDivClassMsCrmG_3// "<div class=\"ms-crm-grid-BodyContainer"...
0x27e33  ldloc.s  6
0x27e35  box      [mscorlib]System.Int32
0x27e3a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27e3f  ldloc.0
0x27e40  ldstr    aDivIdFixedrowC// "<div id=\"fixedrow\" class=\"ms-crm-Lis"...
0x27e45  ldarg.0
0x27e46  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_CssSuffix()
0x27e4b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x27e50  ldstr    asc_42682// "\">"
0x27e55  call     string [mscorlib]System.String::Concat(string, string, string)
0x27e5a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e5f  ldarg.0
0x27e60  ldarg.1
0x27e61  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderColumnHeader(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x27e66  ldloc.0
0x27e67  ldstr    aDivDiv// "</div></div>"
0x27e6c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e71  ldarg.0
0x27e72  callvirt instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Default_Grid_Header_Height()
0x27e77  stloc.3
0x27e78  ldarg.0
0x27e79  ldfld    bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::errorOccured
0x27e7e  brfalse.s loc_27EA8
0x27e80  ldloc.0
0x27e81  ldstr    aDivStyleOverfl_0// "<div style=\"OVERFLOW-X:hidden;\">"
0x27e86  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e8b  ldloc.0
0x27e8c  ldstr    aDivIdFixedrowS// "<div id=\"fixedrow\" style=\"width:100%"...
0x27e91  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27e96  ldarg.0
0x27e97  ldarg.1
0x27e98  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderErrorInnerHtml(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x27e9d  ldloc.0
0x27e9e  ldstr    aDivDiv// "</div></div>"
0x27ea3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27ea8  ldarg.0
0x27ea9  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Expandable()
0x27eae  brtrue.s loc_27EB7
0x27eb0  ldstr    asc_3280A// ""
0x27eb5  br.s     loc_27EBC
0x27eb7  ldstr    aEx// "-Ex"
0x27ebc  stloc.s  5
0x27ebe  ldloc.0
0x27ebf  ldstr    aDivClassMsCrmG_4// "<div class=\"ms-crm-grid-databodycontai"...
0x27ec4  ldloc.3
0x27ec5  box      [mscorlib]System.Int32
0x27eca  ldloc.s  4
0x27ecc  box      [mscorlib]System.Int32
0x27ed1  ldloc.s  5
0x27ed3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object, object)
0x27ed8  ldloc.0
0x27ed9  ldstr    aDivClassMsCrmI_1// "<div class=\"ms-crm-IE7-Height-Fix-Dumm"...
0x27ede  ldloc.s  5
0x27ee0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27ee5  ldloc.0
0x27ee6  ldstr    aDivId// "<div id=\""
0x27eeb  ldarg.0
0x27eec  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x27ef1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x27ef6  ldstr    aDivdatabodyCla// "_divDataBody\" class=\"ms-crm-List-Data"...
0x27efb  call     string [mscorlib]System.String::Concat(string, string, string)
0x27f00  ldloc.s  5
0x27f02  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x27f07  ldarg.0
0x27f08  ldarg.1
0x27f09  ldloc.1
0x27f0a  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderInnerDataBodyHtml(class [System.Web]System.Web.UI.HtmlTextWriter output, class [mscorlib]System.Text.StringBuilder sb)
0x27f0f  ldloc.0
0x27f10  ldstr    aDiv// "</div>"
0x27f15  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27f1a  ldloc.0
0x27f1b  ldstr    aDivDiv// "</div></div>"
0x27f20  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27f25  ldarg.0
0x27f26  ldfld    bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::errorOccured
0x27f2b  brtrue.s loc_27F48
0x27f2d  ldarg.0
0x27f2e  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::CanRenderStatusBar()
0x27f33  brfalse.s loc_27F48
0x27f35  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27f3a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27f3f  brtrue.s loc_27F48
0x27f41  ldarg.0
0x27f42  ldarg.1
0x27f43  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderStatusBar(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x27f48  ldloc.0
0x27f49  ldstr    aDiv// "</div>"
0x27f4e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27f53  ldarg.0
0x27f54  ldfld    bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::errorOccured
0x27f59  ldc.i4.0
0x27f5a  ceq
0x27f5c  ret
```
