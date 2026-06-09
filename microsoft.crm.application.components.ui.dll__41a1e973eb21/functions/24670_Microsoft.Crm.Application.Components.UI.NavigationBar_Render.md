# Microsoft.Crm.Application.Components.UI.NavigationBar::Render

- ea: `0x24670`
- end: `0x24826`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBar::Render`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x243d0`
- `0x243f0`
- `0x24670`
- `0x24830`
- `0x24880`
- `0x24910`
- `0x24c40`
- `0x251f0`

## string_xrefs

- `0x246ef`: `DisableCommandUI`
- `0x24748`: `" class="ms-crm-readForm-navBar-hide`

## pseudocode

```c

```

## disassembly

```asm
0x24670  ldc.i4.0
0x24671  stloc.0
0x24672  ldarg.0
0x24673  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x24678  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0x2467d  stloc.s  4
0x2467f  br.s     loc_246A5
0x24681  ldloc.s  4
0x24683  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x24688  castclass [System.Web]System.Web.UI.Control
0x2468d  isinst   Microsoft.Crm.Application.Components.UI.NavigationBarArea
0x24692  stloc.s  5
0x24694  ldloc.s  5
0x24696  brfalse.s loc_246A5
0x24698  ldloc.0
0x24699  brtrue.s loc_246A5
0x2469b  ldloc.s  5
0x2469d  ldc.i4.1
0x2469e  callvirt instance void Microsoft.Crm.Application.Components.UI.NavigationBarArea::set_IsFirst(bool value)
0x246a3  ldc.i4.1
0x246a4  stloc.0
0x246a5  ldloc.s  4
0x246a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x246ac  brtrue.s loc_24681
0x246ae  leave.s  loc_246C5
0x246b0  ldloc.s  4
0x246b2  isinst   [mscorlib]System.IDisposable
0x246b7  stloc.s  6
0x246b9  ldloc.s  6
0x246bb  brfalse.s loc_246C4
0x246bd  ldloc.s  6
0x246bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x246c4  endfinally
0x246c5  ldarg.1
0x246c6  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x246cb  stloc.1
0x246cc  ldloc.1
0x246cd  ldstr    aDivClassMsCrmF// "<div class=\"ms-crm-FormLeftNav-Standar"...
0x246d2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x246d7  ldarg.0
0x246d8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x246dd  ldloc.1
0x246de  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x246e3  ldloc.1
0x246e4  ldstr    asc_42682// "\">"
0x246e9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x246ee  ldc.i4.1
0x246ef  ldstr    aDisablecommand// "DisableCommandUI"
0x246f4  ldc.i4.0
0x246f5  box      [mscorlib]System.Int32
0x246fa  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x246ff  unbox.any [mscorlib]System.Int32
0x24704  ceq
0x24706  stloc.2
0x24707  ldarg.0
0x24708  call     instance bool Microsoft.Crm.Application.Components.UI.NavigationBar::get_ShowNavBarPaneStrip()
0x2470d  ldloc.2
0x2470e  and
0x2470f  brfalse.s loc_24718
0x24711  ldarg.0
0x24712  ldarg.1
0x24713  call     instance void Microsoft.Crm.Application.Components.UI.NavigationBar::RenderShowHideNavBar(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x24718  ldloc.1
0x24719  ldstr    aDivId// "<div id=\""
0x2471e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x24723  ldarg.0
0x24724  ldstr    aPanetd// "paneTD"
0x24729  call     instance string Microsoft.Crm.Application.Components.UI.NavigationBar::AppendControlId(string id)
0x2472e  ldloc.1
0x2472f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x24734  ldarg.0
0x24735  call     instance bool Microsoft.Crm.Application.Components.UI.NavigationBar::get_ShowNavBarPaneStrip()
0x2473a  brfalse.s loc_24754
0x2473c  ldloc.1
0x2473d  ldstr    aStyleHeight100// "\" style=\"height: 100%; display: none;"...
0x24742  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x24747  ldloc.1
0x24748  ldstr    aClassMsCrmRead// "\" class=\"ms-crm-readForm-navBar-hide"
0x2474d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x24752  br.s     loc_2475F
0x24754  ldloc.1
0x24755  ldstr    aStyleHeight100_0// "\" style=\"height:100%;"
0x2475a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2475f  ldloc.1
0x24760  ldstr    asc_42682// "\">"
0x24765  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2476a  ldarg.0
0x2476b  ldarg.1
0x2476c  call     instance void Microsoft.Crm.Application.Components.UI.NavigationBar::RenderFormSelector(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x24771  ldloc.1
0x24772  ldstr    aDivClassMsCrmF_0// "<div class=\"ms-crm-FormLeftNav-Related"...
0x24777  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2477c  ldloc.1
0x2477d  ldstr    aUlClassMsCrmNa// "<ul class=\"ms-crm-Nav-LeftBar\" id=\""
0x24782  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x24787  ldstr    aCrmformnavsuba// "crmFormNavSubareas"
0x2478c  ldloc.1
0x2478d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x24792  ldloc.1
0x24793  ldstr    asc_4564C// "\" "
0x24798  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2479d  ldc.i4.s 0x1E
0x2479f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x247a4  stloc.3
0x247a5  ldarg.0
0x247a6  call     instance int32 Microsoft.Crm.Application.Components.UI.NavigationBar::get_Width()
0x247ab  ldc.i4   0x82
0x247b0  beq.s    loc_247D7
0x247b2  ldloc.3
0x247b3  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x247b8  ldstr    aWidth0Px// "width:{0}px;"
0x247bd  ldc.i4.1
0x247be  newarr   [mscorlib]System.Object
0x247c3  dup
0x247c4  ldc.i4.0
0x247c5  ldarg.0
0x247c6  call     instance int32 Microsoft.Crm.Application.Components.UI.NavigationBar::get_Width()
0x247cb  box      [mscorlib]System.Int32
0x247d0  stelem.ref
0x247d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x247d6  pop
0x247d7  ldarg.0
0x247d8  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0x247dd  brtrue.s loc_247EB
0x247df  ldloc.3
0x247e0  ldstr    aDisplayNone_0// "display:none;"
0x247e5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x247ea  pop
0x247eb  ldloc.3
0x247ec  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x247f1  ldc.i4.0
0x247f2  ble.s    loc_2480B
0x247f4  ldarg.1
0x247f5  ldstr    aStyle_0// "style"
0x247fa  ldloc.3
0x247fb  callvirt instance string [mscorlib]System.Object::ToString()
0x24800  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x24805  ldc.i4.0
0x24806  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2480b  ldloc.1
0x2480c  ldc.i4.s 0x3E
0x2480e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x24813  ldarg.0
0x24814  ldarg.1
0x24815  callvirt instance void Microsoft.Crm.Application.Components.UI.NavigationBar::RenderChildAreas(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x2481a  ldloc.1
0x2481b  ldstr    aUlDivDivDiv// "</ul></div></div></div>"
0x24820  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x24825  ret
```
