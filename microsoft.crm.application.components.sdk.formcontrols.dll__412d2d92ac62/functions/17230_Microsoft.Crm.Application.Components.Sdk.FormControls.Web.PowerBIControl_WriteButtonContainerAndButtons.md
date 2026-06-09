# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::WriteButtonContainerAndButtons

- ea: `0x17230`
- end: `0x172eb`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::WriteButtonContainerAndButtons`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x17010`

## callees

- `0x15280`
- `0x152d0`
- `0x152f0`
- `0x15310`
- `0x155f0`
- `0x17230`
- `0x172f0`

## pseudocode

```c

```

## disassembly

```asm
0x17230  ldc.i4.s 0x19
0x17232  stloc.0
0x17233  ldloca.s 0
0x17235  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x1723b  callvirt instance string [mscorlib]System.Object::ToString()
0x17240  ldarg.1
0x17241  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::.ctor(string htmlTagName, class [System.Web]System.Web.UI.HtmlTextWriter htmlTextWriter)
0x17246  dup
0x17247  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x1724c  ldc.i4.s 0xA
0x1724e  stloc.1
0x1724f  ldloca.s 1
0x17251  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x17257  callvirt instance string [mscorlib]System.Object::ToString()
0x1725c  ldstr    aMsCrmPowerbiTo_0// "ms-crm-powerbi-toolbar"
0x17261  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x17266  dup
0x17267  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x1726c  ldc.i4.s 0x11
0x1726e  stloc.1
0x1726f  ldloca.s 1
0x17271  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x17277  callvirt instance string [mscorlib]System.Object::ToString()
0x1727c  ldarg.0
0x1727d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x17282  ldstr    aContextualbutt_0// "_ContextualButtonsContainer"
0x17287  call     string [mscorlib]System.String::Concat(string, string)
0x1728c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x17291  dup
0x17292  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x17297  ldc.i4.s 0x2E
0x17299  stloc.1
0x1729a  ldloca.s 1
0x1729c  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x172a2  callvirt instance string [mscorlib]System.Object::ToString()
0x172a7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TextDirection()
0x172ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x172b1  dup
0x172b2  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::Write()
0x172b7  ldarg.0
0x172b8  ldc.i4.0
0x172b9  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::.ctor(valuetype Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonOptions option)
0x172be  ldarg.1
0x172bf  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::WriteButton(class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters buttonParameters, class [System.Web]System.Web.UI.HtmlTextWriter output)
0x172c4  ldarg.0
0x172c5  ldc.i4.1
0x172c6  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::.ctor(valuetype Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonOptions option)
0x172cb  ldarg.1
0x172cc  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::WriteButton(class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters buttonParameters, class [System.Web]System.Web.UI.HtmlTextWriter output)
0x172d1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x172d6  brtrue.s loc_172E5
0x172d8  ldarg.0
0x172d9  ldc.i4.2
0x172da  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::.ctor(valuetype Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonOptions option)
0x172df  ldarg.1
0x172e0  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::WriteButton(class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters buttonParameters, class [System.Web]System.Web.UI.HtmlTextWriter output)
0x172e5  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::WriteEndTag()
0x172ea  ret
```
