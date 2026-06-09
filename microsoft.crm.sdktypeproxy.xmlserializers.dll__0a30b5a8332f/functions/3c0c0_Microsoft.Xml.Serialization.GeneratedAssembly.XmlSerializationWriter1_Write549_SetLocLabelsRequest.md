# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write549_SetLocLabelsRequest

- ea: `0x3c0c0`
- end: `0x3c1d4`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write549_SetLocLabelsRequest`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x5dc0`
- `0x2fdf0`
- `0x3a7a0`
- `0x3c0c0`

## string_xrefs

- `0x3c105`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c11f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c135`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c15a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c172`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c192`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c1a9`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x3c0c0  ldarg.3
0x3c0c1  brtrue.s loc_3C0D0
0x3c0c3  ldarg.s  4
0x3c0c5  brfalse.s loc_3C0CF
0x3c0c7  ldarg.0
0x3c0c8  ldarg.1
0x3c0c9  ldarg.2
0x3c0ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3c0cf  ret
0x3c0d0  ldarg.s  5
0x3c0d2  brtrue.s loc_3C0F0
0x3c0d4  ldarg.3
0x3c0d5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c0da  stloc.0
0x3c0db  ldloc.0
0x3c0dc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetLocLabelsRequest
0x3c0e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c0e6  beq.s    loc_3C0F0
0x3c0e8  ldarg.0
0x3c0e9  ldarg.3
0x3c0ea  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3c0ef  throw
0x3c0f0  ldarg.0
0x3c0f1  ldarg.1
0x3c0f2  ldarg.2
0x3c0f3  ldarg.3
0x3c0f4  ldc.i4.0
0x3c0f5  ldnull
0x3c0f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3c0fb  ldarg.s  5
0x3c0fd  brfalse.s loc_3C10F
0x3c0ff  ldarg.0
0x3c100  ldstr    aSetloclabelsre// "SetLocLabelsRequest"
0x3c105  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c10a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3c10f  ldarg.3
0x3c110  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x3c115  stloc.1
0x3c116  ldloc.1
0x3c117  brfalse.s loc_3C154
0x3c119  ldarg.0
0x3c11a  ldstr    aOptionalparame_0// "OptionalParameters"
0x3c11f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c124  ldnull
0x3c125  ldc.i4.0
0x3c126  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3c12b  ldc.i4.0
0x3c12c  stloc.2
0x3c12d  br.s     loc_3C148
0x3c12f  ldarg.0
0x3c130  ldstr    aOptionalparame// "OptionalParameter"
0x3c135  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c13a  ldloc.1
0x3c13b  ldloc.2
0x3c13c  ldelem.ref
0x3c13d  ldc.i4.1
0x3c13e  ldc.i4.0
0x3c13f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x3c144  ldloc.2
0x3c145  ldc.i4.1
0x3c146  add
0x3c147  stloc.2
0x3c148  ldloc.2
0x3c149  ldloc.1
0x3c14a  ldlen
0x3c14b  conv.i4
0x3c14c  blt.s    loc_3C12F
0x3c14e  ldarg.0
0x3c14f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3c154  ldarg.0
0x3c155  ldstr    aEntitymoniker// "EntityMoniker"
0x3c15a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c15f  ldarg.3
0x3c160  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetLocLabelsRequest::get_EntityMoniker()
0x3c165  ldc.i4.0
0x3c166  ldc.i4.0
0x3c167  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write515_Moniker(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker o, bool isNullable, bool needType)
0x3c16c  ldarg.0
0x3c16d  ldstr    aAttributename// "AttributeName"
0x3c172  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c177  ldarg.3
0x3c178  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetLocLabelsRequest::get_AttributeName()
0x3c17d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3c182  ldarg.3
0x3c183  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.LocLabel[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetLocLabelsRequest::get_Labels()
0x3c188  stloc.3
0x3c189  ldloc.3
0x3c18a  brfalse.s loc_3C1CC
0x3c18c  ldarg.0
0x3c18d  ldstr    aLabels// "Labels"
0x3c192  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c197  ldnull
0x3c198  ldc.i4.0
0x3c199  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3c19e  ldc.i4.0
0x3c19f  stloc.s  4
0x3c1a1  br.s     loc_3C1BF
0x3c1a3  ldarg.0
0x3c1a4  ldstr    aLoclabel// "LocLabel"
0x3c1a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c1ae  ldloc.3
0x3c1af  ldloc.s  4
0x3c1b1  ldelem.ref
0x3c1b2  ldc.i4.1
0x3c1b3  ldc.i4.0
0x3c1b4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write548_LocLabel(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.LocLabel o, bool isNullable, bool needType)
0x3c1b9  ldloc.s  4
0x3c1bb  ldc.i4.1
0x3c1bc  add
0x3c1bd  stloc.s  4
0x3c1bf  ldloc.s  4
0x3c1c1  ldloc.3
0x3c1c2  ldlen
0x3c1c3  conv.i4
0x3c1c4  blt.s    loc_3C1A3
0x3c1c6  ldarg.0
0x3c1c7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3c1cc  ldarg.0
0x3c1cd  ldarg.3
0x3c1ce  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3c1d3  ret
```
