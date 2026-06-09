# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::CreateInnerControl

- ea: `0x4fd0`
- end: `0x5081`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::CreateInnerControl`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x44d0`

## callees

- `0x1330`
- `0x1350`
- `0x1380`
- `0x4fd0`
- `0x8770`

## string_xrefs

- `0x5028`: `ControlActivator created a control which isnt an ASP.NET control`

## pseudocode

```c

```

## disassembly

```asm
0x4fd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fd5  ldstr    a01_1// "{0}{1}_"
0x4fda  ldc.i4.2
0x4fdb  newarr   [mscorlib]System.Object
0x4fe0  dup
0x4fe1  ldc.i4.0
0x4fe2  ldarg.2
0x4fe3  stelem.ref
0x4fe4  dup
0x4fe5  ldc.i4.1
0x4fe6  ldarg.0
0x4fe7  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x4fec  stelem.ref
0x4fed  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4ff2  stloc.0
0x4ff3  ldarg.0
0x4ff4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor, class [System.Web]System.Web.UI.Control> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_controlCache
0x4ff9  ldarg.1
0x4ffa  ldloca.s 1
0x4ffc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor, class [System.Web]System.Web.UI.Control>::TryGetValue(var<u1>, !!T0)
0x5001  brfalse.s loc_5005
0x5003  ldloc.1
0x5004  ret
0x5005  ldarg.1
0x5006  ldarg.0
0x5007  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::get_FormFactor()
0x500c  ldloc.0
0x500d  ldarg.0
0x500e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x5013  ldarg.0
0x5014  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x5019  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ControlActivator::CreateControl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor, string, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor)
0x501e  isinst   [System.Web]System.Web.UI.Control
0x5023  stloc.1
0x5024  ldloc.1
0x5025  brtrue.s loc_5034
0x5027  ldc.i4.0
0x5028  ldstr    aControlactivat// "ControlActivator created a control whic"...
0x502d  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x5032  ldnull
0x5033  ret
0x5034  ldarg.0
0x5035  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor, class [System.Web]System.Web.UI.Control> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_controlCache
0x503a  ldarg.1
0x503b  ldloc.1
0x503c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor, class [System.Web]System.Web.UI.Control>::set_Item(var<u1>, !!T0)
0x5041  ldloc.1
0x5042  isinst   Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase
0x5047  stloc.2
0x5048  ldloc.2
0x5049  brfalse.s loc_5052
0x504b  ldloc.2
0x504c  ldc.i4.1
0x504d  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::set_LayoutMode(valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ControlLayout value)
0x5052  ldloc.1
0x5053  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl
0x5058  stloc.3
0x5059  ldloc.3
0x505a  brfalse.s loc_5067
0x505c  ldloc.3
0x505d  ldc.i4   0x3E8
0x5062  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_TabIndex(int32)
0x5067  ldloc.1
0x5068  isinst   Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ButtonControl
0x506d  stloc.s  4
0x506f  ldloc.s  4
0x5071  brfalse.s loc_507F
0x5073  ldloc.s  4
0x5075  ldstr    aActionstepbutt// "actionStepButton"
0x507a  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ButtonControl::set_CssClass(string value)
0x507f  ldloc.1
0x5080  ret
```
