# Microsoft.Crm.Controls.CommandBarPopup::Render

- ea: `0x11be0`
- end: `0x11c48`
- name: `Microsoft.Crm.Controls.CommandBarPopup::Render`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x116b0`
- `0x11ab0`
- `0x11be0`
- `0x11d80`
- `0x125c0`

## string_xrefs

- `0x11c16`: `The CommandBarType {0} does not have a render method for the CommandBarButton class, please add one.`

## pseudocode

```c

```

## disassembly

```asm
0x11be0  ldarg.0
0x11be1  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0x11be6  brtrue.s loc_11BE9
0x11be8  ret
0x11be9  ldarg.0
0x11bea  call     instance class Microsoft.Crm.Controls.Menu Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x11bef  ldarg.0
0x11bf0  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11bf5  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x11bfa  ldarg.0
0x11bfb  callvirt instance class Microsoft.Crm.Controls.ICrmCommandBar Microsoft.Crm.Controls.CommandBarControl::get_ParentCommandBar()
0x11c00  callvirt instance valuetype Microsoft.Crm.Controls.CommandBarType Microsoft.Crm.Controls.ICrmCommandBar::get_Type()
0x11c05  stloc.0
0x11c06  ldloc.0
0x11c07  brtrue.s loc_11C11
0x11c09  ldarg.0
0x11c0a  ldarg.1
0x11c0b  call     instance void Microsoft.Crm.Controls.CommandBarPopup::RenderForCrmMenuBar(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x11c10  ret
0x11c11  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11c16  ldstr    aTheCommandbart// "The CommandBarType {0} does not have a "...
0x11c1b  ldc.i4.1
0x11c1c  newarr   [mscorlib]System.Object
0x11c21  dup
0x11c22  ldc.i4.0
0x11c23  ldarg.0
0x11c24  callvirt instance class Microsoft.Crm.Controls.ICrmCommandBar Microsoft.Crm.Controls.CommandBarControl::get_ParentCommandBar()
0x11c29  callvirt instance valuetype Microsoft.Crm.Controls.CommandBarType Microsoft.Crm.Controls.ICrmCommandBar::get_Type()
0x11c2e  stloc.0
0x11c2f  ldloca.s 0
0x11c31  constrained. Microsoft.Crm.Controls.CommandBarType
0x11c37  callvirt instance string [mscorlib]System.Object::ToString()
0x11c3c  stelem.ref
0x11c3d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11c42  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x11c47  throw
```
