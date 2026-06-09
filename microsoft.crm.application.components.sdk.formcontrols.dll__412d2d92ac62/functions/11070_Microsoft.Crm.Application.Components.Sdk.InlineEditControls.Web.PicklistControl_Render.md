# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::Render

- ea: `0x11070`
- end: `0x110e9`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::Render`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1330`
- `0x1450`
- `0x8280`
- `0x8e30`
- `0x8e50`
- `0x8e60`
- `0x91b0`
- `0x11070`
- `0x11590`

## pseudocode

```c

```

## disassembly

```asm
0x11070  ldarg.0
0x11071  newobj   instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::.ctor(class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper readFormControl)
0x11076  stloc.0
0x11077  ldarg.0
0x11078  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x1107d  brfalse.s loc_110CC
0x1107f  ldarg.0
0x11080  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x11085  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x1108a  brtrue.s loc_110CC
0x1108c  ldarg.0
0x1108d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x11092  brfalse.s loc_110CC
0x11094  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11099  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x1109e  ldc.i4.2
0x1109f  newarr   [mscorlib]System.Object
0x110a4  dup
0x110a5  ldc.i4.0
0x110a6  ldarg.0
0x110a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x110ac  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x110b1  stelem.ref
0x110b2  dup
0x110b3  ldc.i4.1
0x110b4  ldstr    aRaw// "raw"
0x110b9  stelem.ref
0x110ba  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x110bf  stloc.1
0x110c0  ldloc.0
0x110c1  ldstr    aDataRaw// "data-raw"
0x110c6  ldloc.1
0x110c7  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0x110cc  ldarg.0
0x110cd  ldloc.0
0x110ce  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::RenderPicklistType(class Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer chromeRenderer)
0x110d3  ldloc.0
0x110d4  ldarg.1
0x110d5  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::BeginRender(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x110da  ldarg.0
0x110db  ldarg.1
0x110dc  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.TextControl::Render(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x110e1  ldloc.0
0x110e2  ldarg.1
0x110e3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::EndRender(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x110e8  ret
```
