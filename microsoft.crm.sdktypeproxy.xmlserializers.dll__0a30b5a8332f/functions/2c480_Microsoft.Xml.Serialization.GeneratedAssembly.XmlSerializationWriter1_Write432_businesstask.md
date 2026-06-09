# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write432_businesstask

- ea: `0x2c480`
- end: `0x2c665`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write432_businesstask`
- size: `485`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37e10`
- `0x57310`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16cb0`
- `0x2c480`
- `0x2c670`

## string_xrefs

- `0x2c4c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c4d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c4eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c503`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c51b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c533`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c549`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c55f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c575`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c58d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c5a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c5bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c5d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c5eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c603`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c61b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c633`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c64b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c4fe`: `createdby`
- `0x2c516`: `createdon`
- `0x2c4c0`: `businesstask`
- `0x2c5fe`: `privilege`
- `0x2c4e6`: `businesstaskid`
- `0x2c5e6`: `parentbusinesstaskid`
- `0x2c646`: `taskorder`

## pseudocode

```c

```

## disassembly

```asm
0x2c480  ldarg.3
0x2c481  brtrue.s loc_2C490
0x2c483  ldarg.s  4
0x2c485  brfalse.s loc_2C48F
0x2c487  ldarg.0
0x2c488  ldarg.1
0x2c489  ldarg.2
0x2c48a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2c48f  ret
0x2c490  ldarg.s  5
0x2c492  brtrue.s loc_2C4B0
0x2c494  ldarg.3
0x2c495  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2c49a  stloc.0
0x2c49b  ldloc.0
0x2c49c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask
0x2c4a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c4a6  beq.s    loc_2C4B0
0x2c4a8  ldarg.0
0x2c4a9  ldarg.3
0x2c4aa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2c4af  throw
0x2c4b0  ldarg.0
0x2c4b1  ldarg.1
0x2c4b2  ldarg.2
0x2c4b3  ldarg.3
0x2c4b4  ldc.i4.0
0x2c4b5  ldnull
0x2c4b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2c4bb  ldarg.s  5
0x2c4bd  brfalse.s loc_2C4CF
0x2c4bf  ldarg.0
0x2c4c0  ldstr    aBusinesstask// "businesstask"
0x2c4c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c4ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2c4cf  ldarg.0
0x2c4d0  ldstr    aActionurl// "actionurl"
0x2c4d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c4da  ldarg.3
0x2c4db  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_actionurl()
0x2c4e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c4e5  ldarg.0
0x2c4e6  ldstr    aBusinesstaskid// "businesstaskid"
0x2c4eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c4f0  ldarg.3
0x2c4f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_businesstaskid()
0x2c4f6  ldc.i4.0
0x2c4f7  ldc.i4.0
0x2c4f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2c4fd  ldarg.0
0x2c4fe  ldstr    aCreatedby// "createdby"
0x2c503  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c508  ldarg.3
0x2c509  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_createdby()
0x2c50e  ldc.i4.0
0x2c50f  ldc.i4.0
0x2c510  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2c515  ldarg.0
0x2c516  ldstr    aCreatedon// "createdon"
0x2c51b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c520  ldarg.3
0x2c521  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_createdon()
0x2c526  ldc.i4.0
0x2c527  ldc.i4.0
0x2c528  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2c52d  ldarg.0
0x2c52e  ldstr    aDescription_0// "description"
0x2c533  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c538  ldarg.3
0x2c539  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_description()
0x2c53e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c543  ldarg.0
0x2c544  ldstr    aHelpurl// "helpurl"
0x2c549  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c54e  ldarg.3
0x2c54f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_helpurl()
0x2c554  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c559  ldarg.0
0x2c55a  ldstr    aIconurl// "iconurl"
0x2c55f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c564  ldarg.3
0x2c565  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_iconurl()
0x2c56a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c56f  ldarg.0
0x2c570  ldstr    aLanguagecode_0// "languagecode"
0x2c575  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c57a  ldarg.3
0x2c57b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_languagecode()
0x2c580  ldc.i4.0
0x2c581  ldc.i4.0
0x2c582  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2c587  ldarg.0
0x2c588  ldstr    aModifiedby// "modifiedby"
0x2c58d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c592  ldarg.3
0x2c593  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_modifiedby()
0x2c598  ldc.i4.0
0x2c599  ldc.i4.0
0x2c59a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2c59f  ldarg.0
0x2c5a0  ldstr    aModifiedon// "modifiedon"
0x2c5a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c5aa  ldarg.3
0x2c5ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_modifiedon()
0x2c5b0  ldc.i4.0
0x2c5b1  ldc.i4.0
0x2c5b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2c5b7  ldarg.0
0x2c5b8  ldstr    aName// "name"
0x2c5bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c5c2  ldarg.3
0x2c5c3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_name()
0x2c5c8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c5cd  ldarg.0
0x2c5ce  ldstr    aOrganizationid// "organizationid"
0x2c5d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c5d8  ldarg.3
0x2c5d9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_organizationid()
0x2c5de  ldc.i4.0
0x2c5df  ldc.i4.0
0x2c5e0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2c5e5  ldarg.0
0x2c5e6  ldstr    aParentbusiness_0// "parentbusinesstaskid"
0x2c5eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c5f0  ldarg.3
0x2c5f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_parentbusinesstaskid()
0x2c5f6  ldc.i4.0
0x2c5f7  ldc.i4.0
0x2c5f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2c5fd  ldarg.0
0x2c5fe  ldstr    aPrivilege_0// "privilege"
0x2c603  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c608  ldarg.3
0x2c609  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_privilege()
0x2c60e  ldc.i4.0
0x2c60f  ldc.i4.0
0x2c610  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2c615  ldarg.0
0x2c616  ldstr    aStatecode// "statecode"
0x2c61b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c620  ldarg.3
0x2c621  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BusinessTaskStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_statecode()
0x2c626  ldc.i4.0
0x2c627  ldc.i4.0
0x2c628  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write431_BusinessTaskStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BusinessTaskStateInfo o, bool isNullable, bool needType)
0x2c62d  ldarg.0
0x2c62e  ldstr    aStatuscode// "statuscode"
0x2c633  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c638  ldarg.3
0x2c639  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_statuscode()
0x2c63e  ldc.i4.0
0x2c63f  ldc.i4.0
0x2c640  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x2c645  ldarg.0
0x2c646  ldstr    aTaskorder// "taskorder"
0x2c64b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c650  ldarg.3
0x2c651  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.businesstask::get_taskorder()
0x2c656  ldc.i4.0
0x2c657  ldc.i4.0
0x2c658  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2c65d  ldarg.0
0x2c65e  ldarg.3
0x2c65f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2c664  ret
```
