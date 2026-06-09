# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_Metadata

- ea: `0x14890`
- end: `0x149d2`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_Metadata`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0x1460`
- `0x14810`
- `0x14830`
- `0x14850`
- `0x14870`
- `0x14890`

## pseudocode

```c

```

## disassembly

```asm
0x14890  ldarg.0
0x14891  ldarg.1
0x14892  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x14897  ldarg.0
0x14898  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1489d  brfalse  loc_1499B
0x148a2  ldarg.0
0x148a3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x148a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x148ad  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x148b2  stloc.0
0x148b3  ldloc.0
0x148b4  ldstr    aInt// "int"
0x148b9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x148be  brtrue.s loc_148DF
0x148c0  ldloc.0
0x148c1  ldstr    aDecimal// "decimal"
0x148c6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x148cb  brtrue.s loc_14919
0x148cd  ldloc.0
0x148ce  ldstr    aFloat// "float"
0x148d3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x148d8  brtrue.s loc_1494A
0x148da  br       loc_1497B
0x148df  ldarg.0
0x148e0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x148e5  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata
0x148ea  stloc.1
0x148eb  ldarg.0
0x148ec  ldloc.1
0x148ed  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata::get_MinValue()
0x148f2  conv.r8
0x148f3  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_MinValue(float64 value)
0x148f8  ldarg.0
0x148f9  ldloc.1
0x148fa  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata::get_MaxValue()
0x148ff  conv.r8
0x14900  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_MaxValue(float64 value)
0x14905  ldarg.0
0x14906  ldc.i4.0
0x14907  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_Precision(int32 value)
0x1490c  ldarg.0
0x1490d  ldloc.1
0x1490e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x14913  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_Format(string value)
0x14918  ret
0x14919  ldarg.0
0x1491a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1491f  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata
0x14924  stloc.2
0x14925  ldarg.0
0x14926  ldloc.2
0x14927  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MinValue()
0x1492c  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_MinValue(float64 value)
0x14931  ldarg.0
0x14932  ldloc.2
0x14933  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MaxValue()
0x14938  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_MaxValue(float64 value)
0x1493d  ldarg.0
0x1493e  ldloc.2
0x1493f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_Precision()
0x14944  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_Precision(int32 value)
0x14949  ret
0x1494a  ldarg.0
0x1494b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x14950  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.FloatAttributeMetadata
0x14955  stloc.3
0x14956  ldarg.0
0x14957  ldloc.3
0x14958  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MinValue()
0x1495d  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_MinValue(float64 value)
0x14962  ldarg.0
0x14963  ldloc.3
0x14964  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MaxValue()
0x14969  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_MaxValue(float64 value)
0x1496e  ldarg.0
0x1496f  ldloc.3
0x14970  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_Precision()
0x14975  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_Precision(int32 value)
0x1497a  ret
0x1497b  ldstr    aWrongTypeOfAtt// "Wrong type of attribute UI properties p"...
0x14980  ldarg.0
0x14981  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x14986  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1498b  ldstr    asc_42DAC// "\"."
0x14990  call     string [mscorlib]System.String::Concat(string, string, string)
0x14995  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x1499a  throw
0x1499b  ldarg.0
0x1499c  ldc.r8   -1.797693134862316e308
0x149a5  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_MinValue(float64 value)
0x149aa  ldarg.0
0x149ab  ldc.r8   1.797693134862316e308
0x149b4  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_MaxValue(float64 value)
0x149b9  ldarg.0
0x149ba  ldarg.0
0x149bb  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::DEFAULT_PRECISION
0x149c0  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_Precision(int32 value)
0x149c5  ldarg.0
0x149c6  ldarg.0
0x149c7  ldfld    string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::DEFAULT_FORMAT
0x149cc  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundNumberControl::set_Format(string value)
0x149d1  ret
```
