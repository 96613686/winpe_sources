# Microsoft.Crm.Application.Components.UI.NavigationBar::GetSideStripHtmlAnchor

- ea: `0x24da0`
- end: `0x24e3e`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBar::GetSideStripHtmlAnchor`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x24c60`

## callees

- `0x24c20`
- `0x24da0`
- `0x24e40`

## string_xrefs

- `0x24e24`: `ms-crm-Anchor-SideStrip`

## pseudocode

```c

```

## disassembly

```asm
0x24da0  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0x24da5  stloc.0
0x24da6  ldarg.0
0x24da7  ldloc.0
0x24da8  callvirt instance void Microsoft.Crm.Application.Components.UI.NavigationBar::ModifySideStripAnchorAttributes(class [System.Web]System.Web.UI.HtmlControls.HtmlAnchor anchor)
0x24dad  ldloc.0
0x24dae  ldarg.1
0x24daf  ldstr    aPaneanchor// "_paneAnchor"
0x24db4  call     string [mscorlib]System.String::Concat(string, string)
0x24db9  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24dbe  ldloc.0
0x24dbf  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x24dc4  ldstr    aGrid// "grid"
0x24dc9  ldstr    aFalse// "false"
0x24dce  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x24dd3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24dd8  ldarg.0
0x24dd9  call     instance string Microsoft.Crm.Application.Components.UI.NavigationBar::get_NavigationOnClickAction()
0x24dde  ldc.i4.1
0x24ddf  newarr   [mscorlib]System.Object
0x24de4  dup
0x24de5  ldc.i4.0
0x24de6  ldarg.1
0x24de7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x24dec  stelem.ref
0x24ded  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24df2  stloc.1
0x24df3  ldloc.0
0x24df4  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x24df9  ldstr    aOnclick_0// "onclick"
0x24dfe  ldloc.1
0x24dff  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x24e04  ldloc.0
0x24e05  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x24e0a  ldstr    aHref// "href"
0x24e0f  ldstr    aJavascript// "javascript:;"
0x24e14  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x24e19  ldloc.0
0x24e1a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x24e1f  ldstr    aClass_1// "class"
0x24e24  ldstr    aMsCrmAnchorSid// "ms-crm-Anchor-SideStrip"
0x24e29  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x24e2e  ldloc.0
0x24e2f  stloc.2
0x24e30  leave.s  loc_24E3C
0x24e32  ldloc.0
0x24e33  brfalse.s loc_24E3B
0x24e35  ldloc.0
0x24e36  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24e3b  endfinally
0x24e3c  ldloc.2
0x24e3d  ret
```
