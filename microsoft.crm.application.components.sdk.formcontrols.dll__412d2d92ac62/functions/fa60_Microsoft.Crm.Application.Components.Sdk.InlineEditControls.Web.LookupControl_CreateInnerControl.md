# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::CreateInnerControl

- ea: `0xfa60`
- end: `0xfae1`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::CreateInnerControl`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1330`
- `0x1350`
- `0xed20`
- `0xfa60`

## string_xrefs

- `0xfad3`: `ControlActivator created a control which isn't an ASP.NET control`
- `0xfab5`: `ControlActivator created a control which isn't a link control`

## pseudocode

```c

```

## disassembly

```asm
0xfa60  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfa65  ldstr    a01_1// "{0}{1}_"
0xfa6a  ldc.i4.2
0xfa6b  newarr   [mscorlib]System.Object
0xfa70  dup
0xfa71  ldc.i4.0
0xfa72  ldarg.2
0xfa73  stelem.ref
0xfa74  dup
0xfa75  ldc.i4.1
0xfa76  ldarg.0
0xfa77  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xfa7c  stelem.ref
0xfa7d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xfa82  starg.s  2
0xfa84  ldarg.1
0xfa85  ldarg.0
0xfa86  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::get_FormFactor()
0xfa8b  ldarg.2
0xfa8c  ldarg.0
0xfa8d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0xfa92  ldarg.0
0xfa93  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0xfa98  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ControlActivator::CreateControl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor, string, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor)
0xfa9d  stloc.0
0xfa9e  ldarg.0
0xfa9f  ldloc.0
0xfaa0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::get_ID()
0xfaa5  stfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LookupControl::_linkControlId
0xfaaa  ldloc.0
0xfaab  isinst   Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl
0xfab0  stloc.1
0xfab1  ldloc.1
0xfab2  brtrue.s loc_FAC1
0xfab4  ldc.i4.0
0xfab5  ldstr    aControlactivat_2// "ControlActivator created a control whic"...
0xfaba  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xfabf  br.s     loc_FAC8
0xfac1  ldloc.1
0xfac2  ldc.i4.0
0xfac3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::set_IsEligibleForMarkComplete(bool value)
0xfac8  ldloc.0
0xfac9  isinst   [System.Web]System.Web.UI.Control
0xface  stloc.2
0xfacf  ldloc.2
0xfad0  brtrue.s loc_FADF
0xfad2  ldc.i4.0
0xfad3  ldstr    aControlactivat_1// "ControlActivator created a control whic"...
0xfad8  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xfadd  ldnull
0xfade  ret
0xfadf  ldloc.2
0xfae0  ret
```
