# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write237_resourcespec

- ea: `0x1e540`
- end: `0x1e70f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write237_resourcespec`
- size: `463`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36130`
- `0x554e0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x165c0`
- `0x167c0`
- `0x1e540`

## string_xrefs

- `0x1e585`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e595`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e5ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e5c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e5db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e5f3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e609`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e621`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e639`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e651`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e669`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e67f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e695`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e6ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e6c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e6dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e6f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1e5be`: `createdby`
- `0x1e5d6`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1e540  ldarg.3
0x1e541  brtrue.s loc_1E550
0x1e543  ldarg.s  4
0x1e545  brfalse.s loc_1E54F
0x1e547  ldarg.0
0x1e548  ldarg.1
0x1e549  ldarg.2
0x1e54a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1e54f  ret
0x1e550  ldarg.s  5
0x1e552  brtrue.s loc_1E570
0x1e554  ldarg.3
0x1e555  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1e55a  stloc.0
0x1e55b  ldloc.0
0x1e55c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec
0x1e561  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e566  beq.s    loc_1E570
0x1e568  ldarg.0
0x1e569  ldarg.3
0x1e56a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1e56f  throw
0x1e570  ldarg.0
0x1e571  ldarg.1
0x1e572  ldarg.2
0x1e573  ldarg.3
0x1e574  ldc.i4.0
0x1e575  ldnull
0x1e576  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1e57b  ldarg.s  5
0x1e57d  brfalse.s loc_1E58F
0x1e57f  ldarg.0
0x1e580  ldstr    aResourcespec// "resourcespec"
0x1e585  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e58a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1e58f  ldarg.0
0x1e590  ldstr    aBusinessunitid// "businessunitid"
0x1e595  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e59a  ldarg.3
0x1e59b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_businessunitid()
0x1e5a0  ldc.i4.0
0x1e5a1  ldc.i4.0
0x1e5a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e5a7  ldarg.0
0x1e5a8  ldstr    aConstraints_0// "constraints"
0x1e5ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e5b2  ldarg.3
0x1e5b3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_constraints()
0x1e5b8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e5bd  ldarg.0
0x1e5be  ldstr    aCreatedby// "createdby"
0x1e5c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e5c8  ldarg.3
0x1e5c9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_createdby()
0x1e5ce  ldc.i4.0
0x1e5cf  ldc.i4.0
0x1e5d0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e5d5  ldarg.0
0x1e5d6  ldstr    aCreatedon// "createdon"
0x1e5db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e5e0  ldarg.3
0x1e5e1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_createdon()
0x1e5e6  ldc.i4.0
0x1e5e7  ldc.i4.0
0x1e5e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e5ed  ldarg.0
0x1e5ee  ldstr    aDescription_0// "description"
0x1e5f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e5f8  ldarg.3
0x1e5f9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_description()
0x1e5fe  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e603  ldarg.0
0x1e604  ldstr    aEffortrequired_0// "effortrequired"
0x1e609  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e60e  ldarg.3
0x1e60f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_effortrequired()
0x1e614  ldc.i4.0
0x1e615  ldc.i4.0
0x1e616  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write130_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x1e61b  ldarg.0
0x1e61c  ldstr    aGroupobjectid// "groupobjectid"
0x1e621  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e626  ldarg.3
0x1e627  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_groupobjectid()
0x1e62c  ldc.i4.0
0x1e62d  ldc.i4.0
0x1e62e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1e633  ldarg.0
0x1e634  ldstr    aModifiedby// "modifiedby"
0x1e639  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e63e  ldarg.3
0x1e63f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_modifiedby()
0x1e644  ldc.i4.0
0x1e645  ldc.i4.0
0x1e646  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e64b  ldarg.0
0x1e64c  ldstr    aModifiedon// "modifiedon"
0x1e651  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e656  ldarg.3
0x1e657  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_modifiedon()
0x1e65c  ldc.i4.0
0x1e65d  ldc.i4.0
0x1e65e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1e663  ldarg.0
0x1e664  ldstr    aName// "name"
0x1e669  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e66e  ldarg.3
0x1e66f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_name()
0x1e674  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e679  ldarg.0
0x1e67a  ldstr    aObjectiveexpre_0// "objectiveexpression"
0x1e67f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e684  ldarg.3
0x1e685  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_objectiveexpression()
0x1e68a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1e68f  ldarg.0
0x1e690  ldstr    aObjecttypecode_0// "objecttypecode"
0x1e695  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e69a  ldarg.3
0x1e69b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_objecttypecode()
0x1e6a0  ldc.i4.0
0x1e6a1  ldc.i4.0
0x1e6a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x1e6a7  ldarg.0
0x1e6a8  ldstr    aOrganizationid// "organizationid"
0x1e6ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e6b2  ldarg.3
0x1e6b3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_organizationid()
0x1e6b8  ldc.i4.0
0x1e6b9  ldc.i4.0
0x1e6ba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1e6bf  ldarg.0
0x1e6c0  ldstr    aRequiredcount// "requiredcount"
0x1e6c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e6ca  ldarg.3
0x1e6cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_requiredcount()
0x1e6d0  ldc.i4.0
0x1e6d1  ldc.i4.0
0x1e6d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1e6d7  ldarg.0
0x1e6d8  ldstr    aResourcespecid_0// "resourcespecid"
0x1e6dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e6e2  ldarg.3
0x1e6e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_resourcespecid()
0x1e6e8  ldc.i4.0
0x1e6e9  ldc.i4.0
0x1e6ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1e6ef  ldarg.0
0x1e6f0  ldstr    aSamesite// "samesite"
0x1e6f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1e6fa  ldarg.3
0x1e6fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.resourcespec::get_samesite()
0x1e700  ldc.i4.0
0x1e701  ldc.i4.0
0x1e702  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1e707  ldarg.0
0x1e708  ldarg.3
0x1e709  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1e70e  ret
```
