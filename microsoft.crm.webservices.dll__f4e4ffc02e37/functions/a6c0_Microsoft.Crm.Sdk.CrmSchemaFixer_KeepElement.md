# Microsoft.Crm.Sdk.CrmSchemaFixer::KeepElement

- ea: `0xa6c0`
- end: `0xa727`
- name: `Microsoft.Crm.Sdk.CrmSchemaFixer::KeepElement`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xa510`

## callees

- `0x6ba0`
- `0xa6c0`
- `0xa730`
- `0xa800`

## string_xrefs

- `0xa70b`: `http://schemas.microsoft.com/crm/2006/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa6c0  ldarg.2
0xa6c1  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaElement::get_SchemaTypeName()
0xa6c6  callvirt instance bool [System.Xml]System.Xml.XmlQualifiedName::get_IsEmpty()
0xa6cb  brtrue.s loc_A705
0xa6cd  ldarg.2
0xa6ce  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaType [System.Xml]System.Xml.Schema.XmlSchemaElement::get_SchemaType()
0xa6d3  brtrue.s loc_A705
0xa6d5  ldarg.2
0xa6d6  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaElement::get_RefName()
0xa6db  callvirt instance bool [System.Xml]System.Xml.XmlQualifiedName::get_IsEmpty()
0xa6e0  brfalse.s loc_A705
0xa6e2  ldarg.3
0xa6e3  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::.ctor()
0xa6e8  stind.ref
0xa6e9  ldarg.3
0xa6ea  ldind.ref
0xa6eb  ldarg.2
0xa6ec  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaElement::get_Name()
0xa6f1  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_Name(string)
0xa6f6  ldarg.3
0xa6f7  ldind.ref
0xa6f8  ldarg.2
0xa6f9  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaElement::get_SchemaTypeName()
0xa6fe  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0xa703  ldc.i4.1
0xa704  ret
0xa705  ldarg.1
0xa706  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0xa70b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0xa710  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa715  brfalse.s loc_A71F
0xa717  ldarg.2
0xa718  ldarg.3
0xa719  call     bool Microsoft.Crm.Sdk.CrmSchemaFixer::ProcessCustomSerializedType(class [System.Xml]System.Xml.Schema.XmlSchemaElement element, [out] class [System.Xml]System.Xml.Schema.XmlSchemaElement& target)
0xa71e  ret
0xa71f  ldarg.2
0xa720  ldarg.3
0xa721  call     bool Microsoft.Crm.Sdk.CrmSchemaFixer::ProcessWrappedCustomSerializedType(class [System.Xml]System.Xml.Schema.XmlSchemaElement element, [out] class [System.Xml]System.Xml.Schema.XmlSchemaElement& target)
0xa726  ret
```
