# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1170_lookupmapping

- ea: `0x2f510`
- end: `0x2f69b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1170_lookupmapping`
- size: `395`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x560b0`

## callees

- `0x5cf0`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16cb0`
- `0x2f510`
- `0x2f6a0`

## string_xrefs

- `0x2f555`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f565`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f57d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f595`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f5ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f5c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f5d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f5f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f609`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f621`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f639`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f651`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f669`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f681`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2f578`: `createdby`
- `0x2f590`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x2f510  ldarg.3
0x2f511  brtrue.s loc_2F520
0x2f513  ldarg.s  4
0x2f515  brfalse.s loc_2F51F
0x2f517  ldarg.0
0x2f518  ldarg.1
0x2f519  ldarg.2
0x2f51a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2f51f  ret
0x2f520  ldarg.s  5
0x2f522  brtrue.s loc_2F540
0x2f524  ldarg.3
0x2f525  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2f52a  stloc.0
0x2f52b  ldloc.0
0x2f52c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping
0x2f531  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f536  beq.s    loc_2F540
0x2f538  ldarg.0
0x2f539  ldarg.3
0x2f53a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2f53f  throw
0x2f540  ldarg.0
0x2f541  ldarg.1
0x2f542  ldarg.2
0x2f543  ldarg.3
0x2f544  ldc.i4.0
0x2f545  ldnull
0x2f546  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2f54b  ldarg.s  5
0x2f54d  brfalse.s loc_2F55F
0x2f54f  ldarg.0
0x2f550  ldstr    aLookupmapping// "lookupmapping"
0x2f555  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f55a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2f55f  ldarg.0
0x2f560  ldstr    aColumnmappingi// "columnmappingid"
0x2f565  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f56a  ldarg.3
0x2f56b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_columnmappingid()
0x2f570  ldc.i4.0
0x2f571  ldc.i4.0
0x2f572  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f577  ldarg.0
0x2f578  ldstr    aCreatedby// "createdby"
0x2f57d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f582  ldarg.3
0x2f583  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_createdby()
0x2f588  ldc.i4.0
0x2f589  ldc.i4.0
0x2f58a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f58f  ldarg.0
0x2f590  ldstr    aCreatedon// "createdon"
0x2f595  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f59a  ldarg.3
0x2f59b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_createdon()
0x2f5a0  ldc.i4.0
0x2f5a1  ldc.i4.0
0x2f5a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f5a7  ldarg.0
0x2f5a8  ldstr    aLookupattribut// "lookupattributename"
0x2f5ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f5b2  ldarg.3
0x2f5b3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_lookupattributename()
0x2f5b8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f5bd  ldarg.0
0x2f5be  ldstr    aLookupentityna// "lookupentityname"
0x2f5c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f5c8  ldarg.3
0x2f5c9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_lookupentityname()
0x2f5ce  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2f5d3  ldarg.0
0x2f5d4  ldstr    aLookupmappingi// "lookupmappingid"
0x2f5d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f5de  ldarg.3
0x2f5df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_lookupmappingid()
0x2f5e4  ldc.i4.0
0x2f5e5  ldc.i4.0
0x2f5e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2f5eb  ldarg.0
0x2f5ec  ldstr    aLookupsourceco// "lookupsourcecode"
0x2f5f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f5f6  ldarg.3
0x2f5f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_lookupsourcecode()
0x2f5fc  ldc.i4.0
0x2f5fd  ldc.i4.0
0x2f5fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2f603  ldarg.0
0x2f604  ldstr    aModifiedby// "modifiedby"
0x2f609  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f60e  ldarg.3
0x2f60f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_modifiedby()
0x2f614  ldc.i4.0
0x2f615  ldc.i4.0
0x2f616  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f61b  ldarg.0
0x2f61c  ldstr    aModifiedon// "modifiedon"
0x2f621  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f626  ldarg.3
0x2f627  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_modifiedon()
0x2f62c  ldc.i4.0
0x2f62d  ldc.i4.0
0x2f62e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2f633  ldarg.0
0x2f634  ldstr    aProcesscode// "processcode"
0x2f639  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f63e  ldarg.3
0x2f63f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_processcode()
0x2f644  ldc.i4.0
0x2f645  ldc.i4.0
0x2f646  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2f64b  ldarg.0
0x2f64c  ldstr    aStatecode// "statecode"
0x2f651  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f656  ldarg.3
0x2f657  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LookUpMappingStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_statecode()
0x2f65c  ldc.i4.0
0x2f65d  ldc.i4.0
0x2f65e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1169_LookUpMappingStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LookUpMappingStateInfo o, bool isNullable, bool needType)
0x2f663  ldarg.0
0x2f664  ldstr    aStatuscode// "statuscode"
0x2f669  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f66e  ldarg.3
0x2f66f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_statuscode()
0x2f674  ldc.i4.0
0x2f675  ldc.i4.0
0x2f676  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x2f67b  ldarg.0
0x2f67c  ldstr    aTransformation_2// "transformationparametermappingid"
0x2f681  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2f686  ldarg.3
0x2f687  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.lookupmapping::get_transformationparametermappingid()
0x2f68c  ldc.i4.0
0x2f68d  ldc.i4.0
0x2f68e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2f693  ldarg.0
0x2f694  ldarg.3
0x2f695  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2f69a  ret
```
