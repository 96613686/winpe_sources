# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1234_transformationparametermapping

- ea: `0x2fa90`
- end: `0x2fbed`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1234_transformationparametermapping`
- size: `349`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x57a80`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x2fa90`

## string_xrefs

- `0x2fad5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fae5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fafd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fb15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fb2b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fb43`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fb5b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fb73`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fb8b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fba3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fbbb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fbd3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2fae0`: `createdby`
- `0x2faf8`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x2fa90  ldarg.3
0x2fa91  brtrue.s loc_2FAA0
0x2fa93  ldarg.s  4
0x2fa95  brfalse.s loc_2FA9F
0x2fa97  ldarg.0
0x2fa98  ldarg.1
0x2fa99  ldarg.2
0x2fa9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2fa9f  ret
0x2faa0  ldarg.s  5
0x2faa2  brtrue.s loc_2FAC0
0x2faa4  ldarg.3
0x2faa5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2faaa  stloc.0
0x2faab  ldloc.0
0x2faac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping
0x2fab1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fab6  beq.s    loc_2FAC0
0x2fab8  ldarg.0
0x2fab9  ldarg.3
0x2faba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2fabf  throw
0x2fac0  ldarg.0
0x2fac1  ldarg.1
0x2fac2  ldarg.2
0x2fac3  ldarg.3
0x2fac4  ldc.i4.0
0x2fac5  ldnull
0x2fac6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2facb  ldarg.s  5
0x2facd  brfalse.s loc_2FADF
0x2facf  ldarg.0
0x2fad0  ldstr    aTransformation_1// "transformationparametermapping"
0x2fad5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fada  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2fadf  ldarg.0
0x2fae0  ldstr    aCreatedby// "createdby"
0x2fae5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2faea  ldarg.3
0x2faeb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_createdby()
0x2faf0  ldc.i4.0
0x2faf1  ldc.i4.0
0x2faf2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2faf7  ldarg.0
0x2faf8  ldstr    aCreatedon// "createdon"
0x2fafd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fb02  ldarg.3
0x2fb03  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_createdon()
0x2fb08  ldc.i4.0
0x2fb09  ldc.i4.0
0x2fb0a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2fb0f  ldarg.0
0x2fb10  ldstr    aData_0// "data"
0x2fb15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fb1a  ldarg.3
0x2fb1b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_data()
0x2fb20  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2fb25  ldarg.0
0x2fb26  ldstr    aDatatypecode// "datatypecode"
0x2fb2b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fb30  ldarg.3
0x2fb31  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_datatypecode()
0x2fb36  ldc.i4.0
0x2fb37  ldc.i4.0
0x2fb38  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2fb3d  ldarg.0
0x2fb3e  ldstr    aModifiedby// "modifiedby"
0x2fb43  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fb48  ldarg.3
0x2fb49  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_modifiedby()
0x2fb4e  ldc.i4.0
0x2fb4f  ldc.i4.0
0x2fb50  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2fb55  ldarg.0
0x2fb56  ldstr    aModifiedon// "modifiedon"
0x2fb5b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fb60  ldarg.3
0x2fb61  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_modifiedon()
0x2fb66  ldc.i4.0
0x2fb67  ldc.i4.0
0x2fb68  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2fb6d  ldarg.0
0x2fb6e  ldstr    aParameterarray// "parameterarrayindex"
0x2fb73  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fb78  ldarg.3
0x2fb79  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_parameterarrayindex()
0x2fb7e  ldc.i4.0
0x2fb7f  ldc.i4.0
0x2fb80  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2fb85  ldarg.0
0x2fb86  ldstr    aParameterseque// "parametersequence"
0x2fb8b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fb90  ldarg.3
0x2fb91  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_parametersequence()
0x2fb96  ldc.i4.0
0x2fb97  ldc.i4.0
0x2fb98  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2fb9d  ldarg.0
0x2fb9e  ldstr    aParametertypec// "parametertypecode"
0x2fba3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fba8  ldarg.3
0x2fba9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_parametertypecode()
0x2fbae  ldc.i4.0
0x2fbaf  ldc.i4.0
0x2fbb0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2fbb5  ldarg.0
0x2fbb6  ldstr    aTransformation_3// "transformationmappingid"
0x2fbbb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fbc0  ldarg.3
0x2fbc1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_transformationmappingid()
0x2fbc6  ldc.i4.0
0x2fbc7  ldc.i4.0
0x2fbc8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2fbcd  ldarg.0
0x2fbce  ldstr    aTransformation_2// "transformationparametermappingid"
0x2fbd3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2fbd8  ldarg.3
0x2fbd9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transformationparametermapping::get_transformationparametermappingid()
0x2fbde  ldc.i4.0
0x2fbdf  ldc.i4.0
0x2fbe0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2fbe5  ldarg.0
0x2fbe6  ldarg.3
0x2fbe7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2fbec  ret
```
