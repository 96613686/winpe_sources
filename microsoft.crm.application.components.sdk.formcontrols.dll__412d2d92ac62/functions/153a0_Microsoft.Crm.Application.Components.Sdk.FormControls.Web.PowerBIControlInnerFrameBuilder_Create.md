# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlInnerFrameBuilder::Create

- ea: `0x153a0`
- end: `0x15414`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlInnerFrameBuilder::Create`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x16f40`

## callees

- `0x15420`
- `0x17a20`
- `0x1bff0`
- `0x1c030`
- `0x1c070`
- `0x1c0d0`
- `0x1c170`
- `0x1c1a0`
- `0x1c670`

## pseudocode

```c

```

## disassembly

```asm
0x153a0  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::.ctor()
0x153a5  dup
0x153a6  ldstr    aMsCrmPowerbiIf// "ms-crm-powerbi-iframe"
0x153ab  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_ClassName(string value)
0x153b0  dup
0x153b1  ldarg.1
0x153b2  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_TabIndex(int32 value)
0x153b7  dup
0x153b8  ldc.i4.0
0x153b9  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Security(bool value)
0x153be  dup
0x153bf  ldc.i4.1
0x153c0  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_EnableSandbox(bool value)
0x153c5  dup
0x153c6  ldc.i4.1
0x153c7  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Border(bool value)
0x153cc  dup
0x153cd  ldarg.0
0x153ce  ldarg.2
0x153cf  ldarg.3
0x153d0  ldarg.s  4
0x153d2  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlInnerFrameBuilder::ConstructRuntimeUrl(string tileUrl, string clientId, int32 type)
0x153d7  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Url(string value)
0x153dc  dup
0x153dd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x153e2  dup
0x153e3  ldstr    aAllowScripts// "allow-scripts"
0x153e8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x153ed  dup
0x153ee  ldstr    aAllowSameOrigi// "allow-same-origin"
0x153f3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x153f8  dup
0x153f9  ldstr    aAllowPopups// "allow-popups"
0x153fe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x15403  dup
0x15404  ldstr    aAllowForms// "allow-forms"
0x15409  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1540e  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Sandbox(class [mscorlib]System.Collections.Generic.List`1<string> value)
0x15413  ret
```
