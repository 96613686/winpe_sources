# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::CreateInnerControl

- ea: `0x6310`
- end: `0x638b`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::CreateInnerControl`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1330`
- `0x1350`
- `0x62c0`
- `0x6310`

## string_xrefs

- `0x636b`: `ControlActivator created a control which isn't a quick form control or hidden lookup control `
- `0x637f`: `ControlActivator created a control which isn't an ASP.NET control`

## pseudocode

```c

```

## disassembly

```asm
0x6310  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6315  ldstr    a01_1// "{0}{1}_"
0x631a  ldc.i4.2
0x631b  newarr   [mscorlib]System.Object
0x6320  dup
0x6321  ldc.i4.0
0x6322  ldarg.2
0x6323  stelem.ref
0x6324  dup
0x6325  ldc.i4.1
0x6326  ldarg.0
0x6327  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x632c  stelem.ref
0x632d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6332  starg.s  2
0x6334  ldarg.1
0x6335  ldarg.0
0x6336  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::get_IsInlineEditable()
0x633b  brtrue.s loc_6340
0x633d  ldc.i4.2
0x633e  br.s     loc_6341
0x6340  ldc.i4.3
0x6341  ldarg.2
0x6342  ldarg.0
0x6343  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x6348  ldarg.0
0x6349  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x634e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ControlActivator::CreateControl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor, string, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor)
0x6353  dup
0x6354  isinst   Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl
0x6359  stloc.0
0x635a  dup
0x635b  isinst   Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.HiddenInputControl
0x6360  stloc.1
0x6361  ldloc.0
0x6362  brtrue.s loc_636A
0x6364  ldloc.1
0x6365  ldnull
0x6366  cgt.un
0x6368  br.s     loc_636B
0x636a  ldc.i4.1
0x636b  ldstr    aControlactivat_0// "ControlActivator created a control whic"...
0x6370  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x6375  isinst   [System.Web]System.Web.UI.Control
0x637a  stloc.2
0x637b  ldloc.2
0x637c  ldnull
0x637d  cgt.un
0x637f  ldstr    aControlactivat_1// "ControlActivator created a control whic"...
0x6384  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x6389  ldloc.2
0x638a  ret
```
