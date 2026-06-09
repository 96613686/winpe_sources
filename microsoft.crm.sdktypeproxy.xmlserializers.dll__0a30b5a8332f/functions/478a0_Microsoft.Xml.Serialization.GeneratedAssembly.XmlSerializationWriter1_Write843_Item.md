# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write843_Item

- ea: `0x478a0`
- end: `0x479c5`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write843_Item`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x6600`
- `0x2fdf0`
- `0x478a0`

## string_xrefs

- `0x478e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4791a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x47930`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4795f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x47976`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x479ab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x478e0`: `RetrieveByResourcesServiceRequest`

## pseudocode

```c

```

## disassembly

```asm
0x478a0  ldarg.3
0x478a1  brtrue.s loc_478B0
0x478a3  ldarg.s  4
0x478a5  brfalse.s loc_478AF
0x478a7  ldarg.0
0x478a8  ldarg.1
0x478a9  ldarg.2
0x478aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x478af  ret
0x478b0  ldarg.s  5
0x478b2  brtrue.s loc_478D0
0x478b4  ldarg.3
0x478b5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x478ba  stloc.0
0x478bb  ldloc.0
0x478bc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RetrieveByResourcesServiceRequest
0x478c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x478c6  beq.s    loc_478D0
0x478c8  ldarg.0
0x478c9  ldarg.3
0x478ca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x478cf  throw
0x478d0  ldarg.0
0x478d1  ldarg.1
0x478d2  ldarg.2
0x478d3  ldarg.3
0x478d4  ldc.i4.0
0x478d5  ldnull
0x478d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x478db  ldarg.s  5
0x478dd  brfalse.s loc_478EF
0x478df  ldarg.0
0x478e0  ldstr    aRetrievebyreso// "RetrieveByResourcesServiceRequest"
0x478e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x478ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x478ef  ldarg.0
0x478f0  ldstr    aReturndynamice// "ReturnDynamicEntities"
0x478f5  ldstr    asc_1A34A2// ""
0x478fa  ldarg.3
0x478fb  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RetrieveByResourcesServiceRequest::get_ReturnDynamicEntities()
0x47900  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x47905  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x4790a  ldarg.3
0x4790b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x47910  stloc.1
0x47911  ldloc.1
0x47912  brfalse.s loc_4794F
0x47914  ldarg.0
0x47915  ldstr    aOptionalparame_0// "OptionalParameters"
0x4791a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4791f  ldnull
0x47920  ldc.i4.0
0x47921  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x47926  ldc.i4.0
0x47927  stloc.2
0x47928  br.s     loc_47943
0x4792a  ldarg.0
0x4792b  ldstr    aOptionalparame// "OptionalParameter"
0x47930  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x47935  ldloc.1
0x47936  ldloc.2
0x47937  ldelem.ref
0x47938  ldc.i4.1
0x47939  ldc.i4.0
0x4793a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4793f  ldloc.2
0x47940  ldc.i4.1
0x47941  add
0x47942  stloc.2
0x47943  ldloc.2
0x47944  ldloc.1
0x47945  ldlen
0x47946  conv.i4
0x47947  blt.s    loc_4792A
0x47949  ldarg.0
0x4794a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4794f  ldarg.3
0x47950  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RetrieveByResourcesServiceRequest::get_ResourceIds()
0x47955  stloc.3
0x47956  ldloc.3
0x47957  brfalse.s loc_479A5
0x47959  ldarg.0
0x4795a  ldstr    aResourceids// "ResourceIds"
0x4795f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x47964  ldnull
0x47965  ldc.i4.0
0x47966  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4796b  ldc.i4.0
0x4796c  stloc.s  4
0x4796e  br.s     loc_47998
0x47970  ldarg.0
0x47971  ldstr    aGuid// "guid"
0x47976  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4797b  ldloc.3
0x4797c  ldloc.s  4
0x4797e  ldelema  [mscorlib]System.Guid
0x47983  ldobj    [mscorlib]System.Guid
0x47988  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4798d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x47992  ldloc.s  4
0x47994  ldc.i4.1
0x47995  add
0x47996  stloc.s  4
0x47998  ldloc.s  4
0x4799a  ldloc.3
0x4799b  ldlen
0x4799c  conv.i4
0x4799d  blt.s    loc_47970
0x4799f  ldarg.0
0x479a0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x479a5  ldarg.0
0x479a6  ldstr    aQuery_0// "Query"
0x479ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x479b0  ldarg.3
0x479b1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RetrieveByResourcesServiceRequest::get_Query()
0x479b6  ldc.i4.0
0x479b7  ldc.i4.0
0x479b8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write577_QueryBase(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase o, bool isNullable, bool needType)
0x479bd  ldarg.0
0x479be  ldarg.3
0x479bf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x479c4  ret
```
