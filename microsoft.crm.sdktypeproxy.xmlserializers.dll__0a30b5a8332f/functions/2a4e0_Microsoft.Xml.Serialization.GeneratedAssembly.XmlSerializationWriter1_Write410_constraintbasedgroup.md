# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write410_constraintbasedgroup

- ea: `0x2a4e0`
- end: `0x2a639`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write410_constraintbasedgroup`
- size: `345`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37b00`
- `0x56f20`

## callees

- `0x5cf0`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x2a4e0`

## string_xrefs

- `0x2a525`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a535`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a54d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a565`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a57b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a593`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a5ab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a5c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a5d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a5f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a609`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a61f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2a576`: `createdby`
- `0x2a58e`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x2a4e0  ldarg.3
0x2a4e1  brtrue.s loc_2A4F0
0x2a4e3  ldarg.s  4
0x2a4e5  brfalse.s loc_2A4EF
0x2a4e7  ldarg.0
0x2a4e8  ldarg.1
0x2a4e9  ldarg.2
0x2a4ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2a4ef  ret
0x2a4f0  ldarg.s  5
0x2a4f2  brtrue.s loc_2A510
0x2a4f4  ldarg.3
0x2a4f5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2a4fa  stloc.0
0x2a4fb  ldloc.0
0x2a4fc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup
0x2a501  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a506  beq.s    loc_2A510
0x2a508  ldarg.0
0x2a509  ldarg.3
0x2a50a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2a50f  throw
0x2a510  ldarg.0
0x2a511  ldarg.1
0x2a512  ldarg.2
0x2a513  ldarg.3
0x2a514  ldc.i4.0
0x2a515  ldnull
0x2a516  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2a51b  ldarg.s  5
0x2a51d  brfalse.s loc_2A52F
0x2a51f  ldarg.0
0x2a520  ldstr    aConstraintbase// "constraintbasedgroup"
0x2a525  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a52a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2a52f  ldarg.0
0x2a530  ldstr    aBusinessunitid// "businessunitid"
0x2a535  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a53a  ldarg.3
0x2a53b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_businessunitid()
0x2a540  ldc.i4.0
0x2a541  ldc.i4.0
0x2a542  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2a547  ldarg.0
0x2a548  ldstr    aConstraintbase_0// "constraintbasedgroupid"
0x2a54d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a552  ldarg.3
0x2a553  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_constraintbasedgroupid()
0x2a558  ldc.i4.0
0x2a559  ldc.i4.0
0x2a55a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2a55f  ldarg.0
0x2a560  ldstr    aConstraints_0// "constraints"
0x2a565  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a56a  ldarg.3
0x2a56b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_constraints()
0x2a570  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2a575  ldarg.0
0x2a576  ldstr    aCreatedby// "createdby"
0x2a57b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a580  ldarg.3
0x2a581  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_createdby()
0x2a586  ldc.i4.0
0x2a587  ldc.i4.0
0x2a588  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2a58d  ldarg.0
0x2a58e  ldstr    aCreatedon// "createdon"
0x2a593  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a598  ldarg.3
0x2a599  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_createdon()
0x2a59e  ldc.i4.0
0x2a59f  ldc.i4.0
0x2a5a0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2a5a5  ldarg.0
0x2a5a6  ldstr    aDescription_0// "description"
0x2a5ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a5b0  ldarg.3
0x2a5b1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_description()
0x2a5b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2a5bb  ldarg.0
0x2a5bc  ldstr    aGrouptypecode// "grouptypecode"
0x2a5c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a5c6  ldarg.3
0x2a5c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_grouptypecode()
0x2a5cc  ldc.i4.0
0x2a5cd  ldc.i4.0
0x2a5ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2a5d3  ldarg.0
0x2a5d4  ldstr    aModifiedby// "modifiedby"
0x2a5d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a5de  ldarg.3
0x2a5df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_modifiedby()
0x2a5e4  ldc.i4.0
0x2a5e5  ldc.i4.0
0x2a5e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2a5eb  ldarg.0
0x2a5ec  ldstr    aModifiedon// "modifiedon"
0x2a5f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a5f6  ldarg.3
0x2a5f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_modifiedon()
0x2a5fc  ldc.i4.0
0x2a5fd  ldc.i4.0
0x2a5fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2a603  ldarg.0
0x2a604  ldstr    aName// "name"
0x2a609  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a60e  ldarg.3
0x2a60f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_name()
0x2a614  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2a619  ldarg.0
0x2a61a  ldstr    aOrganizationid// "organizationid"
0x2a61f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2a624  ldarg.3
0x2a625  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.constraintbasedgroup::get_organizationid()
0x2a62a  ldc.i4.0
0x2a62b  ldc.i4.0
0x2a62c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2a631  ldarg.0
0x2a632  ldarg.3
0x2a633  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2a638  ret
```
