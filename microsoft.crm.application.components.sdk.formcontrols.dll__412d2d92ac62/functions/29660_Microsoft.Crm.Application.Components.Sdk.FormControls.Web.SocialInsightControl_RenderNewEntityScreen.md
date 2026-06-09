# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderNewEntityScreen

- ea: `0x29660`
- end: `0x296b0`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderNewEntityScreen`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x293e0`

## callees

- `0x17a10`

## string_xrefs

- `0x29677`: `EmptyGridMessageBoundSubgridCreateRefresh`

## pseudocode

```c

```

## disassembly

```asm
0x29660  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29665  ldstr    aDivIdNewentity// "<div id='newEntityScreen' class='newEnt"...
0x2966a  ldc.i4.2
0x2966b  newarr   [mscorlib]System.Object
0x29670  dup
0x29671  ldc.i4.0
0x29672  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x29677  ldstr    aEmptygridmessa_1// "EmptyGridMessageBoundSubgridCreateRefre"...
0x2967c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x29681  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x29686  stelem.ref
0x29687  dup
0x29688  ldc.i4.1
0x29689  ldarg.0
0x2968a  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2968f  stloc.1
0x29690  ldloca.s 1
0x29692  ldstr    aD// "D"
0x29697  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2969c  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x296a1  stelem.ref
0x296a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x296a7  stloc.0
0x296a8  ldarg.1
0x296a9  ldloc.0
0x296aa  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x296af  ret
```
