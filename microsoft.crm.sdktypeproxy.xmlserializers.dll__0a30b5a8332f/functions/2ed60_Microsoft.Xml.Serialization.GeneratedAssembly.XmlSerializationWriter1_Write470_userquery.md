# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write470_userquery

- ea: `0x2ed60`
- end: `0x2ef2b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write470_userquery`
- size: `459`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x38430`
- `0x57930`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x2ed60`
- `0x2ef30`

## string_xrefs

- `0x2eda5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2edb5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2edcb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ede3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2edfb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ee11`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ee27`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ee3d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ee55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ee6d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ee83`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ee9b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eeb3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eecb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eee1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eef9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ef11`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2edc6`: `createdby`
- `0x2edde`: `createdon`
- `0x2edb0`: `columnsetxml`
- `0x2ee0c`: `fetchxml`
- `0x2ee22`: `layoutxml`

## pseudocode

```c

```

## disassembly

```asm
0x2ed60  ldarg.3
0x2ed61  brtrue.s loc_2ED70
0x2ed63  ldarg.s  4
0x2ed65  brfalse.s loc_2ED6F
0x2ed67  ldarg.0
0x2ed68  ldarg.1
0x2ed69  ldarg.2
0x2ed6a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2ed6f  ret
0x2ed70  ldarg.s  5
0x2ed72  brtrue.s loc_2ED90
0x2ed74  ldarg.3
0x2ed75  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2ed7a  stloc.0
0x2ed7b  ldloc.0
0x2ed7c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery
0x2ed81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ed86  beq.s    loc_2ED90
0x2ed88  ldarg.0
0x2ed89  ldarg.3
0x2ed8a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2ed8f  throw
0x2ed90  ldarg.0
0x2ed91  ldarg.1
0x2ed92  ldarg.2
0x2ed93  ldarg.3
0x2ed94  ldc.i4.0
0x2ed95  ldnull
0x2ed96  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2ed9b  ldarg.s  5
0x2ed9d  brfalse.s loc_2EDAF
0x2ed9f  ldarg.0
0x2eda0  ldstr    aUserquery// "userquery"
0x2eda5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2edaa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2edaf  ldarg.0
0x2edb0  ldstr    aColumnsetxml// "columnsetxml"
0x2edb5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2edba  ldarg.3
0x2edbb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_columnsetxml()
0x2edc0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2edc5  ldarg.0
0x2edc6  ldstr    aCreatedby// "createdby"
0x2edcb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2edd0  ldarg.3
0x2edd1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_createdby()
0x2edd6  ldc.i4.0
0x2edd7  ldc.i4.0
0x2edd8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2eddd  ldarg.0
0x2edde  ldstr    aCreatedon// "createdon"
0x2ede3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ede8  ldarg.3
0x2ede9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_createdon()
0x2edee  ldc.i4.0
0x2edef  ldc.i4.0
0x2edf0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2edf5  ldarg.0
0x2edf6  ldstr    aDescription_0// "description"
0x2edfb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ee00  ldarg.3
0x2ee01  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_description()
0x2ee06  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ee0b  ldarg.0
0x2ee0c  ldstr    aFetchxml_0// "fetchxml"
0x2ee11  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ee16  ldarg.3
0x2ee17  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_fetchxml()
0x2ee1c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ee21  ldarg.0
0x2ee22  ldstr    aLayoutxml// "layoutxml"
0x2ee27  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ee2c  ldarg.3
0x2ee2d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_layoutxml()
0x2ee32  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ee37  ldarg.0
0x2ee38  ldstr    aModifiedby// "modifiedby"
0x2ee3d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ee42  ldarg.3
0x2ee43  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_modifiedby()
0x2ee48  ldc.i4.0
0x2ee49  ldc.i4.0
0x2ee4a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2ee4f  ldarg.0
0x2ee50  ldstr    aModifiedon// "modifiedon"
0x2ee55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ee5a  ldarg.3
0x2ee5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_modifiedon()
0x2ee60  ldc.i4.0
0x2ee61  ldc.i4.0
0x2ee62  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2ee67  ldarg.0
0x2ee68  ldstr    aName// "name"
0x2ee6d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ee72  ldarg.3
0x2ee73  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_name()
0x2ee78  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ee7d  ldarg.0
0x2ee7e  ldstr    aOwnerid// "ownerid"
0x2ee83  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ee88  ldarg.3
0x2ee89  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_ownerid()
0x2ee8e  ldc.i4.0
0x2ee8f  ldc.i4.0
0x2ee90  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2ee95  ldarg.0
0x2ee96  ldstr    aOwningbusiness// "owningbusinessunit"
0x2ee9b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eea0  ldarg.3
0x2eea1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_owningbusinessunit()
0x2eea6  ldc.i4.0
0x2eea7  ldc.i4.0
0x2eea8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2eead  ldarg.0
0x2eeae  ldstr    aQuerytype// "querytype"
0x2eeb3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eeb8  ldarg.3
0x2eeb9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_querytype()
0x2eebe  ldc.i4.0
0x2eebf  ldc.i4.0
0x2eec0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2eec5  ldarg.0
0x2eec6  ldstr    aReturnedtypeco// "returnedtypecode"
0x2eecb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eed0  ldarg.3
0x2eed1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_returnedtypecode()
0x2eed6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2eedb  ldarg.0
0x2eedc  ldstr    aStatecode// "statecode"
0x2eee1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eee6  ldarg.3
0x2eee7  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UserQueryStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_statecode()
0x2eeec  ldc.i4.0
0x2eeed  ldc.i4.0
0x2eeee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write469_UserQueryStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.UserQueryStateInfo o, bool isNullable, bool needType)
0x2eef3  ldarg.0
0x2eef4  ldstr    aStatuscode// "statuscode"
0x2eef9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eefe  ldarg.3
0x2eeff  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_statuscode()
0x2ef04  ldc.i4.0
0x2ef05  ldc.i4.0
0x2ef06  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x2ef0b  ldarg.0
0x2ef0c  ldstr    aUserqueryid// "userqueryid"
0x2ef11  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ef16  ldarg.3
0x2ef17  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.userquery::get_userqueryid()
0x2ef1c  ldc.i4.0
0x2ef1d  ldc.i4.0
0x2ef1e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2ef23  ldarg.0
0x2ef24  ldarg.3
0x2ef25  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2ef2a  ret
```
