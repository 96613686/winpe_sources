# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::GetReportControlFrame

- ea: `0x253d0`
- end: `0x2543e`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::GetReportControlFrame`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x25000`

## callees

- `0x17a10`
- `0x17a20`
- `0x17a80`
- `0x1c0a0`
- `0x1c0d0`
- `0x1c670`
- `0x24e80`

## pseudocode

```c

```

## disassembly

```asm
0x253d0  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::.ctor()
0x253d5  stloc.0
0x253d6  ldloc.0
0x253d7  ldarg.0
0x253d8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x253dd  ldstr    aReportcontrolf_1// "_ReportControlFrame"
0x253e2  call     string [mscorlib]System.String::Concat(string, string)
0x253e7  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x253ec  ldloc.0
0x253ed  ldarg.0
0x253ee  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x253f3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_TabIndex(int32 value)
0x253f8  ldloc.0
0x253f9  ldarg.0
0x253fa  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ReportControl::get_Scrolling()
0x253ff  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Scrolling(string value)
0x25404  ldloc.0
0x25405  ldc.i4.0
0x25406  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Border(bool value)
0x2540b  ldloc.0
0x2540c  ldstr    aWidth// "width"
0x25411  ldstr    a100// "100%"
0x25416  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string name, string value)
0x2541b  ldloc.0
0x2541c  ldstr    aHeight// "height"
0x25421  ldstr    a100// "100%"
0x25426  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string name, string value)
0x2542b  ldloc.0
0x2542c  ldstr    aName// "name"
0x25431  ldloc.0
0x25432  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x25437  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string name, string value)
0x2543c  ldloc.0
0x2543d  ret
```
