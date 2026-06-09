# Microsoft.Crm.Application.Components.UI.NavigationBarItem::Render

- ea: `0x25ab0`
- end: `0x25c51`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBarItem::Render`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1a3b0`
- `0x1a400`
- `0x1a410`
- `0x23c20`
- `0x24210`
- `0x258a0`
- `0x25ab0`
- `0x25c60`
- `0x25c70`

## string_xrefs

- `0x25ac1`: `<li class="ms-crm-Nav-Subarea"><a class="ms-crm-Nav-Subarea-Link`

## pseudocode

```c

```

## disassembly

```asm
0x25ab0  ldarg.0
0x25ab1  call     instance bool Microsoft.Crm.Application.Components.UI.NavigationBarItem::get_Show()
0x25ab6  brtrue.s loc_25AB9
0x25ab8  ret
0x25ab9  ldarg.1
0x25aba  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x25abf  stloc.0
0x25ac0  ldloc.0
0x25ac1  ldstr    aLiClassMsCrmNa// "<li class=\"ms-crm-Nav-Subarea\"><a cla"...
0x25ac6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25acb  ldloc.0
0x25acc  ldarg.0
0x25acd  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x25ad2  brtrue.s loc_25ADB
0x25ad4  ldstr    aHrefTargetSelf// "\" href=\"#\" target=\"_self\" "
0x25ad9  br.s     loc_25AE0
0x25adb  ldstr    aMsCrmNavSubare// " ms-crm-Nav-Subarea-Disabled\" "
0x25ae0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25ae5  ldarg.0
0x25ae6  ldloc.0
0x25ae7  callvirt instance void Microsoft.Crm.Application.Components.UI.NavigationBarItem::ModifySubareaAnchorAttributes(class [mscorlib]System.IO.TextWriter writer)
0x25aec  ldarg.0
0x25aed  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x25af2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25af7  brtrue.s loc_25B18
0x25af9  ldloc.0
0x25afa  ldstr    aId_1// " id=\""
0x25aff  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25b04  ldarg.0
0x25b05  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x25b0a  ldloc.0
0x25b0b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x25b10  ldloc.0
0x25b11  ldc.i4.s 0x22
0x25b13  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x25b18  ldarg.0
0x25b19  ldfld    string Microsoft.Crm.Application.Components.UI.NavigationBarItem::_toolTip
0x25b1e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25b23  brtrue.s loc_25B36
0x25b25  ldstr    aTitle_2// "title"
0x25b2a  ldarg.0
0x25b2b  ldfld    string Microsoft.Crm.Application.Components.UI.NavigationBarItem::_toolTip
0x25b30  ldarg.1
0x25b31  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x25b36  ldarg.0
0x25b37  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x25b3c  brtrue.s loc_25B60
0x25b3e  ldloc.0
0x25b3f  ldstr    aOnclick_1// " onclick=\""
0x25b44  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25b49  ldarg.0
0x25b4a  ldfld    string Microsoft.Crm.Application.Components.UI.NavigationBarItem::_action
0x25b4f  ldloc.0
0x25b50  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x25b55  ldloc.0
0x25b56  ldstr    asc_32802// "\""
0x25b5b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25b60  ldloc.0
0x25b61  ldstr    asc_2B7B6// ">"
0x25b66  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25b6b  ldarg.0
0x25b6c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.NavigationBarItem::_icon
0x25b71  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri source)
0x25b76  stloc.1
0x25b77  ldloc.1
0x25b78  ldstr    aAlt// "alt"
0x25b7d  ldsfld   string [mscorlib]System.String::Empty
0x25b82  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x25b87  ldloc.1
0x25b88  ldstr    aMsCrmNavSubare_0// "ms-crm-Nav-Subarea-Icon"
0x25b8d  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x25b92  ldloc.1
0x25b93  ldstr    aAlign// "align"
0x25b98  ldstr    aAbsmiddle// "absmiddle"
0x25b9d  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x25ba2  ldloc.0
0x25ba3  ldloc.1
0x25ba4  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_OuterHtml()
0x25ba9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25bae  ldloc.0
0x25baf  ldstr    aNobrClassMsCrm_1// "<nobr class=\"ms-crm-Nav-Subarea-Title"...
0x25bb4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25bb9  ldarg.0
0x25bba  ldfld    string Microsoft.Crm.Application.Components.UI.NavigationBarItem::_toolTip
0x25bbf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25bc4  brtrue.s loc_25BD7
0x25bc6  ldstr    aTitle_2// "title"
0x25bcb  ldarg.0
0x25bcc  ldfld    string Microsoft.Crm.Application.Components.UI.NavigationBarItem::_toolTip
0x25bd1  ldarg.1
0x25bd2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x25bd7  ldloc.0
0x25bd8  ldstr    asc_2B7B6// ">"
0x25bdd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25be2  ldloc.0
0x25be3  ldstr    aDivClassMsCrmN// "<div class=\"ms-crm-Nav-Subarea-Title\""...
0x25be8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25bed  ldloc.0
0x25bee  ldarg.0
0x25bef  ldfld    string Microsoft.Crm.Application.Components.UI.NavigationBarItem::_title
0x25bf4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x25bf9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25bfe  ldloc.0
0x25bff  ldstr    aDiv// "</div>"
0x25c04  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25c09  ldloc.0
0x25c0a  ldstr    aNobrA// "</nobr></a>"
0x25c0f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25c14  ldarg.0
0x25c15  callvirt instance void Microsoft.Crm.Application.Components.UI.NavigationBarItem::PreRenderChildren()
0x25c1a  ldarg.0
0x25c1b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x25c20  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::get_Count()
0x25c25  ldc.i4.0
0x25c26  ble.s    loc_25C45
0x25c28  ldloc.0
0x25c29  ldstr    aUl_0// "<ul>"
0x25c2e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25c33  ldarg.0
0x25c34  ldarg.1
0x25c35  callvirt instance void [System.Web]System.Web.UI.Control::RenderChildren(class [System.Web]System.Web.UI.HtmlTextWriter)
0x25c3a  ldloc.0
0x25c3b  ldstr    aUl// "</ul>"
0x25c40  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25c45  ldloc.0
0x25c46  ldstr    aLi// "</li>"
0x25c4b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25c50  ret
```
