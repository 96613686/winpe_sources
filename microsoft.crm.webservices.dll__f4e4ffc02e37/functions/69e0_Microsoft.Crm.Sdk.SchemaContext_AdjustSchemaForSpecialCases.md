# Microsoft.Crm.Sdk.SchemaContext::AdjustSchemaForSpecialCases

- ea: `0x69e0`
- end: `0x6b47`
- name: `Microsoft.Crm.Sdk.SchemaContext::AdjustSchemaForSpecialCases`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6910`

## callees

- `0x69e0`

## string_xrefs

- `0x69e1`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x69e0  ldarg.1
0x69e1  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x69e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x69eb  brfalse  loc_6B46
0x69f0  ldarg.2
0x69f1  isinst   [System.Xml]System.Xml.Schema.XmlSchemaComplexType
0x69f6  stloc.0
0x69f7  ldloc.0
0x69f8  brfalse  loc_6B46
0x69fd  ldloc.0
0x69fe  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaType::get_Name()
0x6a03  ldstr    aArrayofstring// "ArrayOfString"
0x6a08  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a0d  brfalse  loc_6A98
0x6a12  ldloc.0
0x6a13  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaParticle [System.Xml]System.Xml.Schema.XmlSchemaComplexType::get_Particle()
0x6a18  isinst   [System.Xml]System.Xml.Schema.XmlSchemaSequence
0x6a1d  stloc.1
0x6a1e  ldloc.1
0x6a1f  brfalse  loc_6B46
0x6a24  ldloc.1
0x6a25  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x6a2a  brfalse  loc_6B46
0x6a2f  ldloc.1
0x6a30  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x6a35  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::GetEnumerator()
0x6a3a  stloc.2
0x6a3b  br.s     loc_6A77
0x6a3d  ldloc.2
0x6a3e  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::get_Current()
0x6a43  castclass [System.Xml]System.Xml.Schema.XmlSchemaElement
0x6a48  stloc.3
0x6a49  ldloc.3
0x6a4a  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaElement::get_Name()
0x6a4f  ldstr    aTarget// "Target"
0x6a54  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a59  brfalse.s loc_6A77
0x6a5b  ldloc.0
0x6a5c  ldloc.0
0x6a5d  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaType::get_Name()
0x6a62  ldloc.3
0x6a63  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaElement::get_Name()
0x6a68  call     string [mscorlib]System.String::Concat(string, string)
0x6a6d  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaType::set_Name(string)
0x6a72  leave    loc_6B46
0x6a77  ldloc.2
0x6a78  callvirt instance bool [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::MoveNext()
0x6a7d  brtrue.s loc_6A3D
0x6a7f  leave    loc_6B46
0x6a84  ldloc.2
0x6a85  isinst   [mscorlib]System.IDisposable
0x6a8a  stloc.s  4
0x6a8c  ldloc.s  4
0x6a8e  brfalse.s loc_6A97
0x6a90  ldloc.s  4
0x6a92  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a97  endfinally
0x6a98  ldloc.0
0x6a99  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaType::get_Name()
0x6a9e  ldstr    aLookupattribut// "LookupAttributeMetadata"
0x6aa3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6aa8  brfalse  loc_6B46
0x6aad  ldloc.0
0x6aae  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaContentModel [System.Xml]System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x6ab3  isinst   [System.Xml]System.Xml.Schema.XmlSchemaComplexContent
0x6ab8  stloc.s  5
0x6aba  ldloc.s  5
0x6abc  brfalse  loc_6B46
0x6ac1  ldloc.s  5
0x6ac3  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaContent [System.Xml]System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x6ac8  castclass [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension
0x6acd  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaParticle [System.Xml]System.Xml.Schema.XmlSchemaComplexContentExtension::get_Particle()
0x6ad2  isinst   [System.Xml]System.Xml.Schema.XmlSchemaSequence
0x6ad7  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x6adc  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::GetEnumerator()
0x6ae1  stloc.2
0x6ae2  br.s     loc_6B28
0x6ae4  ldloc.2
0x6ae5  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::get_Current()
0x6aea  castclass [System.Xml]System.Xml.Schema.XmlSchemaElement
0x6aef  stloc.s  6
0x6af1  ldloc.s  6
0x6af3  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaElement::get_SchemaTypeName()
0x6af8  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x6afd  ldstr    aArrayofstring// "ArrayOfString"
0x6b02  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b07  brfalse.s loc_6B28
0x6b09  ldloc.s  6
0x6b0b  ldstr    aArrayofstringt// "ArrayOfStringTarget"
0x6b10  ldloc.s  6
0x6b12  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaElement::get_SchemaTypeName()
0x6b17  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x6b1c  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x6b21  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class [System.Xml]System.Xml.XmlQualifiedName)
0x6b26  leave.s  loc_6B46
0x6b28  ldloc.2
0x6b29  callvirt instance bool [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::MoveNext()
0x6b2e  brtrue.s loc_6AE4
0x6b30  leave.s  loc_6B46
0x6b32  ldloc.2
0x6b33  isinst   [mscorlib]System.IDisposable
0x6b38  stloc.s  4
0x6b3a  ldloc.s  4
0x6b3c  brfalse.s loc_6B45
0x6b3e  ldloc.s  4
0x6b40  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b45  endfinally
0x6b46  ret
```
