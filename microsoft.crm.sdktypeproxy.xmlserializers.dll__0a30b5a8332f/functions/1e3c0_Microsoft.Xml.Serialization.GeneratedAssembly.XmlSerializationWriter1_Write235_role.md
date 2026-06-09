# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write235_role

- ea: `0x1e3c0`
- end: `0x1e535`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write235_role`
- size: `373`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x360c0`
- `0x55470`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x1e3c0`

## string_xrefs

- `0x1e405`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e415`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e42d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e445`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e45d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e475`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e48d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e4a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e4bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e4d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e4eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e503`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e51b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e428`: `createdby`
- `0x1e440`: `createdon`
- `0x1e4ce`: `overriddencreatedon`
- `0x1e516`: `roletemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x1e3c0  ldarg.3
0x1e3c1  brtrue.s loc_1E3D0
0x1e3c3  ldarg.s  4
0x1e3c5  brfalse.s loc_1E3CF
0x1e3c7  ldarg.0
0x1e3c8  ldarg.1
0x1e3c9  ldarg.2
0x1e3ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1e3cf  ret
0x1e3d0  ldarg.s  5
0x1e3d2  brtrue.s loc_1E3F0
0x1e3d4  ldarg.3
0x1e3d5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1e3da  stloc.0
0x1e3db  ldloc.0
0x1e3dc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role
0x1e3e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e3e6  beq.s    loc_1E3F0
0x1e3e8  ldarg.0
0x1e3e9  ldarg.3
0x1e3ea  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1e3ef  throw
0x1e3f0  ldarg.0
0x1e3f1  ldarg.1
0x1e3f2  ldarg.2
0x1e3f3  ldarg.3
0x1e3f4  ldc.i4.0
0x1e3f5  ldnull
0x1e3f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1e3fb  ldarg.s  5
0x1e3fd  brfalse.s loc_1E40F
0x1e3ff  ldarg.0
0x1e400  ldstr    aRole// "role"
0x1e405  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e40a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1e40f  ldarg.0
0x1e410  ldstr    aBusinessunitid// "businessunitid"
0x1e415  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e41a  ldarg.3
0x1e41b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_businessunitid()
0x1e420  ldc.i4.0
0x1e421  ldc.i4.0
0x1e422  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e427  ldarg.0
0x1e428  ldstr    aCreatedby// "createdby"
0x1e42d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e432  ldarg.3
0x1e433  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_createdby()
0x1e438  ldc.i4.0
0x1e439  ldc.i4.0
0x1e43a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e43f  ldarg.0
0x1e440  ldstr    aCreatedon// "createdon"
0x1e445  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e44a  ldarg.3
0x1e44b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_createdon()
0x1e450  ldc.i4.0
0x1e451  ldc.i4.0
0x1e452  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e457  ldarg.0
0x1e458  ldstr    aImportsequence// "importsequencenumber"
0x1e45d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e462  ldarg.3
0x1e463  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_importsequencenumber()
0x1e468  ldc.i4.0
0x1e469  ldc.i4.0
0x1e46a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1e46f  ldarg.0
0x1e470  ldstr    aModifiedby// "modifiedby"
0x1e475  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e47a  ldarg.3
0x1e47b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_modifiedby()
0x1e480  ldc.i4.0
0x1e481  ldc.i4.0
0x1e482  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e487  ldarg.0
0x1e488  ldstr    aModifiedon// "modifiedon"
0x1e48d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e492  ldarg.3
0x1e493  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_modifiedon()
0x1e498  ldc.i4.0
0x1e499  ldc.i4.0
0x1e49a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e49f  ldarg.0
0x1e4a0  ldstr    aName// "name"
0x1e4a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e4aa  ldarg.3
0x1e4ab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_name()
0x1e4b0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e4b5  ldarg.0
0x1e4b6  ldstr    aOrganizationid// "organizationid"
0x1e4bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e4c0  ldarg.3
0x1e4c1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_organizationid()
0x1e4c6  ldc.i4.0
0x1e4c7  ldc.i4.0
0x1e4c8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1e4cd  ldarg.0
0x1e4ce  ldstr    aOverriddencrea// "overriddencreatedon"
0x1e4d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e4d8  ldarg.3
0x1e4d9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_overriddencreatedon()
0x1e4de  ldc.i4.0
0x1e4df  ldc.i4.0
0x1e4e0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e4e5  ldarg.0
0x1e4e6  ldstr    aParentroleid// "parentroleid"
0x1e4eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e4f0  ldarg.3
0x1e4f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_parentroleid()
0x1e4f6  ldc.i4.0
0x1e4f7  ldc.i4.0
0x1e4f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e4fd  ldarg.0
0x1e4fe  ldstr    aRoleid// "roleid"
0x1e503  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e508  ldarg.3
0x1e509  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_roleid()
0x1e50e  ldc.i4.0
0x1e50f  ldc.i4.0
0x1e510  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1e515  ldarg.0
0x1e516  ldstr    aRoletemplateid// "roletemplateid"
0x1e51b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e520  ldarg.3
0x1e521  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.role::get_roletemplateid()
0x1e526  ldc.i4.0
0x1e527  ldc.i4.0
0x1e528  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e52d  ldarg.0
0x1e52e  ldarg.3
0x1e52f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1e534  ret
```
