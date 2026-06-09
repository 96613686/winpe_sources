# Microsoft.Crm.Application.Components.UI.Grid.DataGrid::Render

- ea: `0x27750`
- end: `0x2797b`
- name: `Microsoft.Crm.Application.Components.UI.Grid.DataGrid::Render`
- size: `555`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x271b0`
- `0x27450`
- `0x27740`
- `0x27750`
- `0x27d60`
- `0x281d0`
- `0x281e0`
- `0x29570`
- `0x296c0`
- `0x29850`
- `0x2a190`

## string_xrefs

- `0x277c2`: `MSIE 8.0`

## pseudocode

```c

```

## disassembly

```asm
0x27750  ldarg.1
0x27751  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x27756  stloc.0
0x27757  ldarg.0
0x27758  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Expandable()
0x2775d  brtrue.s loc_27766
0x2775f  ldstr    asc_3280A// ""
0x27764  br.s     loc_2776B
0x27766  ldstr    aEx// "-Ex"
0x2776b  stloc.1
0x2776c  ldstr    aOverflowHidden// "overflow:hidden;"
0x27771  stloc.2
0x27772  ldarg.0
0x27773  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x27778  brfalse.s loc_277D6
0x2777a  ldarg.0
0x2777b  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x27780  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x27785  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x2778a  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x2778f  ldstr    aIe// "IE"
0x27794  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27799  brfalse.s loc_277D6
0x2779b  ldarg.0
0x2779c  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x277a1  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x277a6  callvirt instance string [System.Web]System.Web.HttpRequest::get_UserAgent()
0x277ab  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x277b0  brtrue.s loc_277D6
0x277b2  ldarg.0
0x277b3  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x277b8  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x277bd  callvirt instance string [System.Web]System.Web.HttpRequest::get_UserAgent()
0x277c2  ldstr    aMsie80// "MSIE 8.0"
0x277c7  ldc.i4.5
0x277c8  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x277cd  ldc.i4.m1
0x277ce  ble.s    loc_277D6
0x277d0  ldsfld   string [mscorlib]System.String::Empty
0x277d5  stloc.2
0x277d6  ldloc.0
0x277d7  ldstr    aDivClassMsCrmG// "<div class=\"ms-crm-grid-BodyContainer"...
0x277dc  ldloc.2
0x277dd  ldarg.0
0x277de  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataSetContainer()
0x277e3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x277e8  ldarg.0
0x277e9  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x277ee  ldloc.0
0x277ef  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x277f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x277f9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x277fe  brfalse.s loc_2786C
0x27800  ldloc.0
0x27801  ldstr    aClassMsCrmList// "\" class=\"ms-crm-ListControl{0}\" type"...
0x27806  ldloc.1
0x27807  ldarg.0
0x27808  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_CssSuffix()
0x2780d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x27812  call     string [mscorlib]System.String::Concat(string, string)
0x27817  ldarg.0
0x27818  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataSetContainer()
0x2781d  ldsfld   string [mscorlib]System.String::Empty
0x27822  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27827  brtrue.s loc_27844
0x27829  ldarg.0
0x2782a  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataSetContainer()
0x2782f  ldarg.0
0x27830  ldfld    string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::StyleDisplayNone
0x27835  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2783a  brtrue.s loc_27844
0x2783c  ldarg.0
0x2783d  ldfld    string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::StyleDisplayNone
0x27842  br.s     loc_27849
0x27844  ldsfld   string [mscorlib]System.String::Empty
0x27849  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x2784e  ldloc.0
0x2784f  ldstr    aDivClassMsCrmG_0// "<div class=\"ms-crm-grid-body{1}\" styl"...
0x27854  ldarg.0
0x27855  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2785a  ldstr    aGridbodycontai// "_gridBodyContainer"
0x2785f  call     string [mscorlib]System.String::Concat(string, string)
0x27864  ldloc.1
0x27865  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x2786a  br.s     loc_278E1
0x2786c  ldloc.0
0x2786d  ldstr    aClassMsCrmList_0// "\" class=\"ms-crm-ListControl{0}\" type"...
0x27872  ldloc.1
0x27873  ldarg.0
0x27874  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_CssSuffix()
0x27879  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2787e  call     string [mscorlib]System.String::Concat(string, string)
0x27883  ldarg.0
0x27884  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataSetContainer()
0x27889  ldsfld   string [mscorlib]System.String::Empty
0x2788e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27893  brtrue.s loc_278B0
0x27895  ldarg.0
0x27896  callvirt instance string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_DataSetContainer()
0x2789b  ldarg.0
0x2789c  ldfld    string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::StyleDisplayNone
0x278a1  callvirt instance bool [mscorlib]System.String::Contains(string)
0x278a6  brtrue.s loc_278B0
0x278a8  ldarg.0
0x278a9  ldfld    string Microsoft.Crm.Application.Components.UI.Grid.DataGrid::StyleDisplayNone
0x278ae  br.s     loc_278B5
0x278b0  ldsfld   string [mscorlib]System.String::Empty
0x278b5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x278ba  ldloc.0
0x278bb  ldstr    aDivClassMsCrmG_1// "<div class=\"ms-crm-grid-body{2}\" styl"...
0x278c0  ldarg.0
0x278c1  callvirt instance int32 Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_FooterRowHeight()
0x278c6  box      [mscorlib]System.Int32
0x278cb  ldarg.0
0x278cc  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x278d1  ldstr    aGridbodycontai// "_gridBodyContainer"
0x278d6  call     string [mscorlib]System.String::Concat(string, string)
0x278db  ldloc.1
0x278dc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object, object)
0x278e1  ldarg.0
0x278e2  ldarg.0
0x278e3  ldarg.1
0x278e4  callvirt instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderInnerHtml(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x278e9  ldc.i4.0
0x278ea  ceq
0x278ec  stfld    bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::errorOccured
0x278f1  ldloc.0
0x278f2  ldstr    aDiv// "</div>"
0x278f7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x278fc  ldarg.0
0x278fd  ldloc.0
0x278fe  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderPropertiesForm(class [mscorlib]System.IO.TextWriter writer)
0x27903  ldarg.0
0x27904  ldloc.0
0x27905  call     instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderParametersForm(class [mscorlib]System.IO.TextWriter writer)
0x2790a  ldloc.0
0x2790b  ldstr    aDivDiv// "</div></div>"
0x27910  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27915  ldarg.0
0x27916  ldfld    bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::errorOccured
0x2791b  brtrue.s loc_27939
0x2791d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27922  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27927  brtrue.s loc_27932
0x27929  ldarg.0
0x2792a  ldarg.1
0x2792b  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderFooterRow(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x27930  br.s     loc_27939
0x27932  ldarg.0
0x27933  ldarg.1
0x27934  callvirt instance void Microsoft.Crm.Application.Components.UI.Grid.DataGrid::RenderStatusBar(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x27939  ldarg.0
0x2793a  call     instance bool Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_EnableExportToExcel()
0x2793f  brfalse.s loc_2796F
0x27941  ldarg.1
0x27942  ldstr    aDivStyleDispla_0// "<div style=\"display:none\"><iframe id="...
0x27947  ldstr    aStaticBlankHtm// "/_static/blank.htm"
0x2794c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27951  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27956  callvirt instance string [mscorlib]System.Object::ToString()
0x2795b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x27960  ldstr    aIframeDiv// "\"></iframe></div>"
0x27965  call     string [mscorlib]System.String::Concat(string, string, string)
0x2796a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2796f  ldloc.0
0x27970  ldstr    aDivDiv// "</div></div>"
0x27975  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2797a  ret
```
