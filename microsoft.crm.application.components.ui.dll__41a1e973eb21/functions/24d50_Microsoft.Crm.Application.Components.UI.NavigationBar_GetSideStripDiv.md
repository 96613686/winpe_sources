# Microsoft.Crm.Application.Components.UI.NavigationBar::GetSideStripDiv

- ea: `0x24d50`
- end: `0x24d91`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBar::GetSideStripDiv`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x24c60`

## callees

- `0x24d50`

## string_xrefs

- `0x24d77`: `ms-crm-control-SideStrip`

## pseudocode

```c

```

## disassembly

```asm
0x24d50  ldstr    aDiv_4// "div"
0x24d55  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x24d5a  stloc.0
0x24d5b  ldloc.0
0x24d5c  ldarg.0
0x24d5d  ldstr    aPanestripdiv// "_paneStripDiv"
0x24d62  call     string [mscorlib]System.String::Concat(string, string)
0x24d67  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24d6c  ldloc.0
0x24d6d  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x24d72  ldstr    aClass_1// "class"
0x24d77  ldstr    aMsCrmControlSi// "ms-crm-control-SideStrip"
0x24d7c  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x24d81  ldloc.0
0x24d82  stloc.1
0x24d83  leave.s  loc_24D8F
0x24d85  ldloc.0
0x24d86  brfalse.s loc_24D8E
0x24d88  ldloc.0
0x24d89  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24d8e  endfinally
0x24d8f  ldloc.1
0x24d90  ret
```
