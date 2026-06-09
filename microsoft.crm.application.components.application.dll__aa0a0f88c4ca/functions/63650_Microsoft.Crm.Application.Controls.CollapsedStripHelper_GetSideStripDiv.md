# Microsoft.Crm.Application.Controls.CollapsedStripHelper::GetSideStripDiv

- ea: `0x63650`
- end: `0x63719`
- name: `Microsoft.Crm.Application.Controls.CollapsedStripHelper::GetSideStripDiv`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x62a10`
- `0x62af0`

## callees

- `0x63650`

## string_xrefs

- `0x6367a`: `window.Mscrm && Mscrm.CompositeControl && Mscrm.CompositeControl.glowGridStrip(true, '`
- `0x6369a`: `window.Mscrm && Mscrm.CompositeControl && Mscrm.CompositeControl.glowGridStrip(false, '`
- `0x636cd`: `window.Mscrm && Mscrm.CompositeControl && Mscrm.CompositeControl.glowPaneStrip(true, '`
- `0x636ed`: `window.Mscrm && Mscrm.CompositeControl && Mscrm.CompositeControl.glowPaneStrip(false, '`
- `0x6370d`: `ms-crm-control-SideStrip`

## pseudocode

```c

```

## disassembly

```asm
0x63650  ldstr    aDiv_3// "div"
0x63655  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x6365a  stloc.0
0x6365b  ldarg.0
0x6365c  brfalse.s loc_636B1
0x6365e  ldloc.0
0x6365f  ldarg.2
0x63660  ldstr    aGridstripdiv// "_gridStripDiv"
0x63665  call     string [mscorlib]System.String::Concat(string, string)
0x6366a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x6366f  ldloc.0
0x63670  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x63675  ldstr    aOnmouseover// "onmouseover"
0x6367a  ldstr    aWindowMscrmMsc_0// "window.Mscrm && Mscrm.CompositeControl "...
0x6367f  ldarg.1
0x63680  ldstr    asc_11BB62// "');"
0x63685  call     string [mscorlib]System.String::Concat(string, string, string)
0x6368a  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x6368f  ldloc.0
0x63690  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x63695  ldstr    aOnmouseout// "onmouseout"
0x6369a  ldstr    aWindowMscrmMsc_1// "window.Mscrm && Mscrm.CompositeControl "...
0x6369f  ldarg.1
0x636a0  ldstr    asc_11BB62// "');"
0x636a5  call     string [mscorlib]System.String::Concat(string, string, string)
0x636aa  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x636af  br.s     loc_63702
0x636b1  ldloc.0
0x636b2  ldarg.2
0x636b3  ldstr    aPanestripdiv// "_paneStripDiv"
0x636b8  call     string [mscorlib]System.String::Concat(string, string)
0x636bd  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x636c2  ldloc.0
0x636c3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x636c8  ldstr    aOnmouseover// "onmouseover"
0x636cd  ldstr    aWindowMscrmMsc_2// "window.Mscrm && Mscrm.CompositeControl "...
0x636d2  ldarg.1
0x636d3  ldstr    asc_11BB62// "');"
0x636d8  call     string [mscorlib]System.String::Concat(string, string, string)
0x636dd  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x636e2  ldloc.0
0x636e3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x636e8  ldstr    aOnmouseout// "onmouseout"
0x636ed  ldstr    aWindowMscrmMsc_3// "window.Mscrm && Mscrm.CompositeControl "...
0x636f2  ldarg.1
0x636f3  ldstr    asc_11BB62// "');"
0x636f8  call     string [mscorlib]System.String::Concat(string, string, string)
0x636fd  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x63702  ldloc.0
0x63703  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x63708  ldstr    aClass_0// "class"
0x6370d  ldstr    aMsCrmControlSi// "ms-crm-control-SideStrip"
0x63712  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x63717  ldloc.0
0x63718  ret
```
