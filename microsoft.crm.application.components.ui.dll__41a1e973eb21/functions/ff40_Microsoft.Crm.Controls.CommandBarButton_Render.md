# Microsoft.Crm.Controls.CommandBarButton::Render

- ea: `0xff40`
- end: `0xffa7`
- name: `Microsoft.Crm.Controls.CommandBarButton::Render`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xff40`
- `0x101a0`
- `0x116b0`
- `0x125c0`

## string_xrefs

- `0xff75`: `The CommandBarType {0} does not have a render method for the CommandBarButton class, please add one.`

## pseudocode

```c

```

## disassembly

```asm
0xff40  ldarg.0
0xff41  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0xff46  brtrue.s loc_FF49
0xff48  ret
0xff49  ldarg.0
0xff4a  callvirt instance class Microsoft.Crm.Controls.ICrmCommandBar Microsoft.Crm.Controls.CommandBarControl::get_ParentCommandBar()
0xff4f  brtrue.s loc_FF59
0xff51  ldarg.0
0xff52  ldarg.1
0xff53  call     instance void Microsoft.Crm.Controls.CommandBarButton::RenderForCrmMenuBar(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xff58  ret
0xff59  ldarg.0
0xff5a  callvirt instance class Microsoft.Crm.Controls.ICrmCommandBar Microsoft.Crm.Controls.CommandBarControl::get_ParentCommandBar()
0xff5f  callvirt instance valuetype Microsoft.Crm.Controls.CommandBarType Microsoft.Crm.Controls.ICrmCommandBar::get_Type()
0xff64  stloc.0
0xff65  ldloc.0
0xff66  brtrue.s loc_FF70
0xff68  ldarg.0
0xff69  ldarg.1
0xff6a  call     instance void Microsoft.Crm.Controls.CommandBarButton::RenderForCrmMenuBar(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xff6f  ret
0xff70  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xff75  ldstr    aTheCommandbart// "The CommandBarType {0} does not have a "...
0xff7a  ldc.i4.1
0xff7b  newarr   [mscorlib]System.Object
0xff80  dup
0xff81  ldc.i4.0
0xff82  ldarg.0
0xff83  callvirt instance class Microsoft.Crm.Controls.ICrmCommandBar Microsoft.Crm.Controls.CommandBarControl::get_ParentCommandBar()
0xff88  callvirt instance valuetype Microsoft.Crm.Controls.CommandBarType Microsoft.Crm.Controls.ICrmCommandBar::get_Type()
0xff8d  stloc.0
0xff8e  ldloca.s 0
0xff90  constrained. Microsoft.Crm.Controls.CommandBarType
0xff96  callvirt instance string [mscorlib]System.Object::ToString()
0xff9b  stelem.ref
0xff9c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xffa1  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xffa6  throw
```
