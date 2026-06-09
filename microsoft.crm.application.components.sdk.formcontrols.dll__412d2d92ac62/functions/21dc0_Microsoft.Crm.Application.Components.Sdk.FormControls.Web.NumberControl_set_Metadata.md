# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_Metadata

- ea: `0x21dc0`
- end: `0x21ec3`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_Metadata`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1edc0`
- `0x20d10`

## callees

- `0x182d0`
- `0x182e0`
- `0x21dc0`
- `0x21ef0`
- `0x21f30`
- `0x21f70`

## pseudocode

```c

```

## disassembly

```asm
0x21dc0  ldarg.0
0x21dc1  ldarg.1
0x21dc2  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x21dc7  ldarg.0
0x21dc8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x21dcd  brfalse  loc_21E98
0x21dd2  ldarg.0
0x21dd3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x21dd8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x21ddd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x21de2  stloc.0
0x21de3  ldloc.0
0x21de4  ldstr    aInt// "int"
0x21de9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21dee  brtrue.s loc_21E19
0x21df0  ldloc.0
0x21df1  ldstr    aDecimal// "decimal"
0x21df6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21dfb  brtrue.s loc_21E47
0x21dfd  ldloc.0
0x21dfe  ldstr    aFloat// "float"
0x21e03  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21e08  brtrue.s loc_21E47
0x21e0a  ldloc.0
0x21e0b  ldstr    aMoney// "money"
0x21e10  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21e15  brtrue.s loc_21E47
0x21e17  br.s     loc_21E78
0x21e19  ldarg.0
0x21e1a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x21e1f  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata
0x21e24  stloc.1
0x21e25  ldarg.0
0x21e26  ldloc.1
0x21e27  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata::get_MinValue()
0x21e2c  conv.r8
0x21e2d  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_MinValue(float64 value)
0x21e32  ldarg.0
0x21e33  ldloc.1
0x21e34  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata::get_MaxValue()
0x21e39  conv.r8
0x21e3a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_MaxValue(float64 value)
0x21e3f  ldarg.0
0x21e40  ldc.i4.0
0x21e41  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_Precision(int32 value)
0x21e46  ret
0x21e47  ldarg.0
0x21e48  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x21e4d  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata
0x21e52  stloc.2
0x21e53  ldarg.0
0x21e54  ldloc.2
0x21e55  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MinValue()
0x21e5a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_MinValue(float64 value)
0x21e5f  ldarg.0
0x21e60  ldloc.2
0x21e61  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MaxValue()
0x21e66  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_MaxValue(float64 value)
0x21e6b  ldarg.0
0x21e6c  ldloc.2
0x21e6d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_Precision()
0x21e72  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_Precision(int32 value)
0x21e77  ret
0x21e78  ldstr    aWrongTypeOfAtt// "Wrong type of attribute UI properties p"...
0x21e7d  ldarg.0
0x21e7e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x21e83  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x21e88  ldstr    asc_42DAC// "\"."
0x21e8d  call     string [mscorlib]System.String::Concat(string, string, string)
0x21e92  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x21e97  throw
0x21e98  ldarg.0
0x21e99  ldc.r8   -1.797693134862316e308
0x21ea2  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_MinValue(float64 value)
0x21ea7  ldarg.0
0x21ea8  ldc.r8   1.797693134862316e308
0x21eb1  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_MaxValue(float64 value)
0x21eb6  ldarg.0
0x21eb7  ldarg.0
0x21eb8  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::DEFAULT_PRECISION
0x21ebd  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NumberControl::set_Precision(int32 value)
0x21ec2  ret
```
