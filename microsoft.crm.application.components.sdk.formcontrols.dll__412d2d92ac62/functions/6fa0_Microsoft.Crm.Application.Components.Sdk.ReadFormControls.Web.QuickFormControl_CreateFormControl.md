# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::CreateFormControl

- ea: `0x6fa0`
- end: `0x702c`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::CreateFormControl`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x6b80`

## callees

- `0x1290`
- `0x6910`
- `0x6b30`
- `0x6b40`
- `0x6fa0`
- `0x72c0`

## string_xrefs

- `0x6fae`: `If QuickFormDescriptor is null, QuickFormControl.CreateFormControl shouldnt even be called. FormId={0}`

## pseudocode

```c

```

## disassembly

```asm
0x6fa0  ldarg.0
0x6fa1  ldfld    class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_quickFormDescriptor
0x6fa6  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor>::get_Value()
0x6fab  ldnull
0x6fac  cgt.un
0x6fae  ldstr    aIfQuickformdes_0// "If QuickFormDescriptor is null, QuickFo"...
0x6fb3  ldc.i4.1
0x6fb4  newarr   [mscorlib]System.Object
0x6fb9  dup
0x6fba  ldc.i4.0
0x6fbb  ldarg.0
0x6fbc  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_FormId()
0x6fc1  box      [mscorlib]System.Guid
0x6fc6  stelem.ref
0x6fc7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x6fcc  ldarg.0
0x6fcd  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x6fd2  ldstr    asc_359D6// "_"
0x6fd7  call     string [mscorlib]System.String::Concat(string, string)
0x6fdc  ldarg.0
0x6fdd  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_FormDataEntityId()
0x6fe2  ldarg.0
0x6fe3  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x6fe8  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.ReadFormNoNotifications::.ctor(string, string, int32)
0x6fed  dup
0x6fee  ldc.i4.1
0x6fef  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm::set_RenderOnlyBody(bool)
0x6ff4  dup
0x6ff5  ldarg.0
0x6ff6  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_IsInlineEditable()
0x6ffb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::set_InlineEditable(bool)
0x7000  dup
0x7001  ldarg.0
0x7002  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_FormId()
0x7007  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.ReadForm::Execute(valuetype [mscorlib]System.Guid)
0x700c  dup
0x700d  ldarg.0
0x700e  ldfld    valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControlMode Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_controlMode
0x7013  ldc.i4.3
0x7014  beq.s    loc_7019
0x7016  ldc.i4.0
0x7017  br.s     loc_701A
0x7019  ldc.i4.1
0x701a  stfld    bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.ReadFormNoNotifications::IsQuickFormCreateControlMode
0x701f  dup
0x7020  ldarg.0
0x7021  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_IsTurboForm()
0x7026  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::set_IsTurboForm(bool)
0x702b  ret
```
