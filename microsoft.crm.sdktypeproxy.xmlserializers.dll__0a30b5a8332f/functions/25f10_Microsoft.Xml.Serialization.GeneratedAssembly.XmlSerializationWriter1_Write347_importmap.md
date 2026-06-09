# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write347_importmap

- ea: `0x25f10`
- end: `0x26123`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write347_importmap`
- size: `531`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37160`
- `0x565f0`

## callees

- `0x5cf0`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x25f10`
- `0x26130`

## string_xrefs

- `0x25f55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25f65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25f7d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25f95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25fab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25fc3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25fdb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25ff3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2600b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26023`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2603b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26051`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26069`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26081`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26097`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x260ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x260c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x260db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x260f3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2610b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x25f60`: `createdby`
- `0x25f78`: `createdon`
- `0x25fee`: `iswizardcreated`
- `0x26092`: `sourceuseridentifierforsourcecrmuserlink`
- `0x260a8`: `sourceuseridentifierforsourcedatasourceuserlink`
- `0x26106`: `targetuseridentifierforsourcecrmuserlink`

## pseudocode

```c

```

## disassembly

```asm
0x25f10  ldarg.3
0x25f11  brtrue.s loc_25F20
0x25f13  ldarg.s  4
0x25f15  brfalse.s loc_25F1F
0x25f17  ldarg.0
0x25f18  ldarg.1
0x25f19  ldarg.2
0x25f1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x25f1f  ret
0x25f20  ldarg.s  5
0x25f22  brtrue.s loc_25F40
0x25f24  ldarg.3
0x25f25  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x25f2a  stloc.0
0x25f2b  ldloc.0
0x25f2c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap
0x25f31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25f36  beq.s    loc_25F40
0x25f38  ldarg.0
0x25f39  ldarg.3
0x25f3a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x25f3f  throw
0x25f40  ldarg.0
0x25f41  ldarg.1
0x25f42  ldarg.2
0x25f43  ldarg.3
0x25f44  ldc.i4.0
0x25f45  ldnull
0x25f46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x25f4b  ldarg.s  5
0x25f4d  brfalse.s loc_25F5F
0x25f4f  ldarg.0
0x25f50  ldstr    aImportmap// "importmap"
0x25f55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25f5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x25f5f  ldarg.0
0x25f60  ldstr    aCreatedby// "createdby"
0x25f65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25f6a  ldarg.3
0x25f6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_createdby()
0x25f70  ldc.i4.0
0x25f71  ldc.i4.0
0x25f72  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x25f77  ldarg.0
0x25f78  ldstr    aCreatedon// "createdon"
0x25f7d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25f82  ldarg.3
0x25f83  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_createdon()
0x25f88  ldc.i4.0
0x25f89  ldc.i4.0
0x25f8a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x25f8f  ldarg.0
0x25f90  ldstr    aDescription_0// "description"
0x25f95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25f9a  ldarg.3
0x25f9b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_description()
0x25fa0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x25fa5  ldarg.0
0x25fa6  ldstr    aImportmapid// "importmapid"
0x25fab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25fb0  ldarg.3
0x25fb1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_importmapid()
0x25fb6  ldc.i4.0
0x25fb7  ldc.i4.0
0x25fb8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x25fbd  ldarg.0
0x25fbe  ldstr    aImportmaptype// "importmaptype"
0x25fc3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25fc8  ldarg.3
0x25fc9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_importmaptype()
0x25fce  ldc.i4.0
0x25fcf  ldc.i4.0
0x25fd0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x25fd5  ldarg.0
0x25fd6  ldstr    aIsvalidforimpo// "isvalidforimport"
0x25fdb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25fe0  ldarg.3
0x25fe1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_isvalidforimport()
0x25fe6  ldc.i4.0
0x25fe7  ldc.i4.0
0x25fe8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x25fed  ldarg.0
0x25fee  ldstr    aIswizardcreate// "iswizardcreated"
0x25ff3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x25ff8  ldarg.3
0x25ff9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_iswizardcreated()
0x25ffe  ldc.i4.0
0x25fff  ldc.i4.0
0x26000  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x26005  ldarg.0
0x26006  ldstr    aModifiedby// "modifiedby"
0x2600b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26010  ldarg.3
0x26011  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_modifiedby()
0x26016  ldc.i4.0
0x26017  ldc.i4.0
0x26018  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2601d  ldarg.0
0x2601e  ldstr    aModifiedon// "modifiedon"
0x26023  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26028  ldarg.3
0x26029  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_modifiedon()
0x2602e  ldc.i4.0
0x2602f  ldc.i4.0
0x26030  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x26035  ldarg.0
0x26036  ldstr    aName// "name"
0x2603b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26040  ldarg.3
0x26041  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_name()
0x26046  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2604b  ldarg.0
0x2604c  ldstr    aOwnerid// "ownerid"
0x26051  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26056  ldarg.3
0x26057  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_ownerid()
0x2605c  ldc.i4.0
0x2605d  ldc.i4.0
0x2605e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x26063  ldarg.0
0x26064  ldstr    aOwningbusiness// "owningbusinessunit"
0x26069  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2606e  ldarg.3
0x2606f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_owningbusinessunit()
0x26074  ldc.i4.0
0x26075  ldc.i4.0
0x26076  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2607b  ldarg.0
0x2607c  ldstr    aSource// "source"
0x26081  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26086  ldarg.3
0x26087  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_source()
0x2608c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x26091  ldarg.0
0x26092  ldstr    aSourceuseriden// "sourceuseridentifierforsourcecrmuserlin"...
0x26097  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2609c  ldarg.3
0x2609d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_sourceuseridentifierforsourcecrmuserlink()
0x260a2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x260a7  ldarg.0
0x260a8  ldstr    aSourceuseriden_0// "sourceuseridentifierforsourcedatasource"...
0x260ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x260b2  ldarg.3
0x260b3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_sourceuseridentifierforsourcedatasourceuserlink()
0x260b8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x260bd  ldarg.0
0x260be  ldstr    aStatecode// "statecode"
0x260c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x260c8  ldarg.3
0x260c9  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportMapStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_statecode()
0x260ce  ldc.i4.0
0x260cf  ldc.i4.0
0x260d0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write346_ImportMapStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportMapStateInfo o, bool isNullable, bool needType)
0x260d5  ldarg.0
0x260d6  ldstr    aStatuscode// "statuscode"
0x260db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x260e0  ldarg.3
0x260e1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_statuscode()
0x260e6  ldc.i4.0
0x260e7  ldc.i4.0
0x260e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x260ed  ldarg.0
0x260ee  ldstr    aTargetentity// "targetentity"
0x260f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x260f8  ldarg.3
0x260f9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_targetentity()
0x260fe  ldc.i4.0
0x260ff  ldc.i4.0
0x26100  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x26105  ldarg.0
0x26106  ldstr    aTargetuseriden// "targetuseridentifierforsourcecrmuserlin"...
0x2610b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26110  ldarg.3
0x26111  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.importmap::get_targetuseridentifierforsourcecrmuserlink()
0x26116  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2611b  ldarg.0
0x2611c  ldarg.3
0x2611d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x26122  ret
```
