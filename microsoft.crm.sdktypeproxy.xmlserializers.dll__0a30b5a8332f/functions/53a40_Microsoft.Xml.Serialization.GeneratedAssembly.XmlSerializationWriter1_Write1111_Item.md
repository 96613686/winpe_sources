# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1111_Item

- ea: `0x53a40`
- end: `0x53b84`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1111_Item`
- size: `324`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x19ce0`
- `0x2fdf0`
- `0x346f0`
- `0x53a40`

## string_xrefs

- `0x53a85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53a9f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53ab5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53ada`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53af2`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53b0a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53b22`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53b3a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53b52`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53b6a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53a80`: `CreateWithMappingImportMapRequest`

## pseudocode

```c

```

## disassembly

```asm
0x53a40  ldarg.3
0x53a41  brtrue.s loc_53A50
0x53a43  ldarg.s  4
0x53a45  brfalse.s loc_53A4F
0x53a47  ldarg.0
0x53a48  ldarg.1
0x53a49  ldarg.2
0x53a4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x53a4f  ret
0x53a50  ldarg.s  5
0x53a52  brtrue.s loc_53A70
0x53a54  ldarg.3
0x53a55  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x53a5a  stloc.0
0x53a5b  ldloc.0
0x53a5c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWithMappingImportMapRequest
0x53a61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53a66  beq.s    loc_53A70
0x53a68  ldarg.0
0x53a69  ldarg.3
0x53a6a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x53a6f  throw
0x53a70  ldarg.0
0x53a71  ldarg.1
0x53a72  ldarg.2
0x53a73  ldarg.3
0x53a74  ldc.i4.0
0x53a75  ldnull
0x53a76  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x53a7b  ldarg.s  5
0x53a7d  brfalse.s loc_53A8F
0x53a7f  ldarg.0
0x53a80  ldstr    aCreatewithmapp// "CreateWithMappingImportMapRequest"
0x53a85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53a8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x53a8f  ldarg.3
0x53a90  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x53a95  stloc.1
0x53a96  ldloc.1
0x53a97  brfalse.s loc_53AD4
0x53a99  ldarg.0
0x53a9a  ldstr    aOptionalparame_0// "OptionalParameters"
0x53a9f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53aa4  ldnull
0x53aa5  ldc.i4.0
0x53aa6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x53aab  ldc.i4.0
0x53aac  stloc.2
0x53aad  br.s     loc_53AC8
0x53aaf  ldarg.0
0x53ab0  ldstr    aOptionalparame// "OptionalParameter"
0x53ab5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53aba  ldloc.1
0x53abb  ldloc.2
0x53abc  ldelem.ref
0x53abd  ldc.i4.1
0x53abe  ldc.i4.0
0x53abf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x53ac4  ldloc.2
0x53ac5  ldc.i4.1
0x53ac6  add
0x53ac7  stloc.2
0x53ac8  ldloc.2
0x53ac9  ldloc.1
0x53aca  ldlen
0x53acb  conv.i4
0x53acc  blt.s    loc_53AAF
0x53ace  ldarg.0
0x53acf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x53ad4  ldarg.0
0x53ad5  ldstr    aImportmap_0// "ImportMap"
0x53ada  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53adf  ldarg.3
0x53ae0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWithMappingImportMapRequest::get_ImportMap()
0x53ae5  ldc.i4.0
0x53ae6  ldc.i4.0
0x53ae7  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write132_BusinessEntity(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity o, bool isNullable, bool needType)
0x53aec  ldarg.0
0x53aed  ldstr    aColumnmappings_1// "ColumnMappings"
0x53af2  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53af7  ldarg.3
0x53af8  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWithMappingImportMapRequest::get_ColumnMappings()
0x53afd  ldc.i4.0
0x53afe  ldc.i4.0
0x53aff  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write179_BusinessEntityCollection(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection o, bool isNullable, bool needType)
0x53b04  ldarg.0
0x53b05  ldstr    aPicklistmappin_3// "PickListMappings"
0x53b0a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53b0f  ldarg.3
0x53b10  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWithMappingImportMapRequest::get_PickListMappings()
0x53b15  ldc.i4.0
0x53b16  ldc.i4.0
0x53b17  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write179_BusinessEntityCollection(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection o, bool isNullable, bool needType)
0x53b1c  ldarg.0
0x53b1d  ldstr    aLookupmappings_1// "LookUpMappings"
0x53b22  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53b27  ldarg.3
0x53b28  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWithMappingImportMapRequest::get_LookUpMappings()
0x53b2d  ldc.i4.0
0x53b2e  ldc.i4.0
0x53b2f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write179_BusinessEntityCollection(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection o, bool isNullable, bool needType)
0x53b34  ldarg.0
0x53b35  ldstr    aOwnermappings// "OwnerMappings"
0x53b3a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53b3f  ldarg.3
0x53b40  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWithMappingImportMapRequest::get_OwnerMappings()
0x53b45  ldc.i4.0
0x53b46  ldc.i4.0
0x53b47  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write179_BusinessEntityCollection(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection o, bool isNullable, bool needType)
0x53b4c  ldarg.0
0x53b4d  ldstr    aTransformation_6// "TransformationMappings"
0x53b52  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53b57  ldarg.3
0x53b58  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWithMappingImportMapRequest::get_TransformationMappings()
0x53b5d  ldc.i4.0
0x53b5e  ldc.i4.0
0x53b5f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write179_BusinessEntityCollection(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection o, bool isNullable, bool needType)
0x53b64  ldarg.0
0x53b65  ldstr    aTransformation_7// "TransformationParameterMappings"
0x53b6a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53b6f  ldarg.3
0x53b70  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWithMappingImportMapRequest::get_TransformationParameterMappings()
0x53b75  ldc.i4.0
0x53b76  ldc.i4.0
0x53b77  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write179_BusinessEntityCollection(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection o, bool isNullable, bool needType)
0x53b7c  ldarg.0
0x53b7d  ldarg.3
0x53b7e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x53b83  ret
```
