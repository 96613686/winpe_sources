# Microsoft.Crm.Workflow.InteractionActivityResult::InteractionActivityResultXml

- ea: `0xe770`
- end: `0xe81b`
- name: `Microsoft.Crm.Workflow.InteractionActivityResult::InteractionActivityResultXml`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe0e0`

## callees

- `0xe650`
- `0xe670`
- `0xe6f0`
- `0xe770`
- `0xeda0`

## pseudocode

```c

```

## disassembly

```asm
0xe770  ldstr    aInteractionact// "<interactionActivity name=\"{0}\" type="...
0xe775  stloc.0
0xe776  ldarg.0
0xe777  call     instance object Microsoft.Crm.Workflow.InteractionActivityResult::get_ResponseValue()
0xe77c  brfalse.s loc_E7D2
0xe77e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe783  ldloc.0
0xe784  ldc.i4.4
0xe785  newarr   [mscorlib]System.Object
0xe78a  dup
0xe78b  ldc.i4.0
0xe78c  ldarg.0
0xe78d  call     instance string Microsoft.Crm.Workflow.InteractionActivityResult::get_Name()
0xe792  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0xe797  stelem.ref
0xe798  dup
0xe799  ldc.i4.1
0xe79a  ldarg.0
0xe79b  ldfld    int32 Microsoft.Crm.Workflow.InteractionActivityResult::_responseMetadataType
0xe7a0  call     string Microsoft.Crm.Workflow.PageTypeConvertors::GetResponseMetadata(int32 responseMetadataType)
0xe7a5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0xe7aa  stelem.ref
0xe7ab  dup
0xe7ac  ldc.i4.2
0xe7ad  ldarg.0
0xe7ae  call     instance object Microsoft.Crm.Workflow.InteractionActivityResult::get_ResponseValue()
0xe7b3  callvirt instance string [mscorlib]System.Object::ToString()
0xe7b8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0xe7bd  stelem.ref
0xe7be  dup
0xe7bf  ldc.i4.3
0xe7c0  ldarg.0
0xe7c1  call     instance string Microsoft.Crm.Workflow.InteractionActivityResult::get_PromptText()
0xe7c6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0xe7cb  stelem.ref
0xe7cc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe7d1  ret
0xe7d2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe7d7  ldloc.0
0xe7d8  ldc.i4.4
0xe7d9  newarr   [mscorlib]System.Object
0xe7de  dup
0xe7df  ldc.i4.0
0xe7e0  ldarg.0
0xe7e1  call     instance string Microsoft.Crm.Workflow.InteractionActivityResult::get_Name()
0xe7e6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0xe7eb  stelem.ref
0xe7ec  dup
0xe7ed  ldc.i4.1
0xe7ee  ldarg.0
0xe7ef  ldfld    int32 Microsoft.Crm.Workflow.InteractionActivityResult::_responseMetadataType
0xe7f4  call     string Microsoft.Crm.Workflow.PageTypeConvertors::GetResponseMetadata(int32 responseMetadataType)
0xe7f9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0xe7fe  stelem.ref
0xe7ff  dup
0xe800  ldc.i4.2
0xe801  ldstr    asc_30690// ""
0xe806  stelem.ref
0xe807  dup
0xe808  ldc.i4.3
0xe809  ldarg.0
0xe80a  call     instance string Microsoft.Crm.Workflow.InteractionActivityResult::get_PromptText()
0xe80f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0xe814  stelem.ref
0xe815  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe81a  ret
```
