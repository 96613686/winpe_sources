# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write223_savedquery

- ea: `0x1d4f0`
- end: `0x1d761`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write223_savedquery`
- size: `625`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35e90`
- `0x55240`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x1d4f0`

## string_xrefs

- `0x1d535`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d545`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d55b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d573`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d58b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d5a3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d5b9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d5cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d5e7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d5ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d617`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d62f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d647`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d65f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d675`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d68d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d6a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d6bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d6d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d6e9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d701`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d719`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d72f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d747`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1d556`: `createdby`
- `0x1d56e`: `createdon`
- `0x1d540`: `columnsetxml`
- `0x1d5b4`: `fetchxml`
- `0x1d65a`: `layoutxml`

## pseudocode

```c

```

## disassembly

```asm
0x1d4f0  ldarg.3
0x1d4f1  brtrue.s loc_1D500
0x1d4f3  ldarg.s  4
0x1d4f5  brfalse.s loc_1D4FF
0x1d4f7  ldarg.0
0x1d4f8  ldarg.1
0x1d4f9  ldarg.2
0x1d4fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1d4ff  ret
0x1d500  ldarg.s  5
0x1d502  brtrue.s loc_1D520
0x1d504  ldarg.3
0x1d505  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1d50a  stloc.0
0x1d50b  ldloc.0
0x1d50c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery
0x1d511  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d516  beq.s    loc_1D520
0x1d518  ldarg.0
0x1d519  ldarg.3
0x1d51a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1d51f  throw
0x1d520  ldarg.0
0x1d521  ldarg.1
0x1d522  ldarg.2
0x1d523  ldarg.3
0x1d524  ldc.i4.0
0x1d525  ldnull
0x1d526  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1d52b  ldarg.s  5
0x1d52d  brfalse.s loc_1D53F
0x1d52f  ldarg.0
0x1d530  ldstr    aSavedquery// "savedquery"
0x1d535  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d53a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1d53f  ldarg.0
0x1d540  ldstr    aColumnsetxml// "columnsetxml"
0x1d545  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d54a  ldarg.3
0x1d54b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_columnsetxml()
0x1d550  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d555  ldarg.0
0x1d556  ldstr    aCreatedby// "createdby"
0x1d55b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d560  ldarg.3
0x1d561  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_createdby()
0x1d566  ldc.i4.0
0x1d567  ldc.i4.0
0x1d568  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d56d  ldarg.0
0x1d56e  ldstr    aCreatedon// "createdon"
0x1d573  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d578  ldarg.3
0x1d579  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_createdon()
0x1d57e  ldc.i4.0
0x1d57f  ldc.i4.0
0x1d580  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1d585  ldarg.0
0x1d586  ldstr    aCustomizationl// "customizationlevel"
0x1d58b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d590  ldarg.3
0x1d591  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_customizationlevel()
0x1d596  ldc.i4.0
0x1d597  ldc.i4.0
0x1d598  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1d59d  ldarg.0
0x1d59e  ldstr    aDescription_0// "description"
0x1d5a3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d5a8  ldarg.3
0x1d5a9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_description()
0x1d5ae  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d5b3  ldarg.0
0x1d5b4  ldstr    aFetchxml_0// "fetchxml"
0x1d5b9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d5be  ldarg.3
0x1d5bf  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_fetchxml()
0x1d5c4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d5c9  ldarg.0
0x1d5ca  ldstr    aInproduction// "inproduction"
0x1d5cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d5d4  ldarg.3
0x1d5d5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_inproduction()
0x1d5da  ldc.i4.0
0x1d5db  ldc.i4.0
0x1d5dc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1d5e1  ldarg.0
0x1d5e2  ldstr    aIscustomizable// "iscustomizable"
0x1d5e7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d5ec  ldarg.3
0x1d5ed  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_iscustomizable()
0x1d5f2  ldc.i4.0
0x1d5f3  ldc.i4.0
0x1d5f4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1d5f9  ldarg.0
0x1d5fa  ldstr    aIsdefault// "isdefault"
0x1d5ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d604  ldarg.3
0x1d605  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_isdefault()
0x1d60a  ldc.i4.0
0x1d60b  ldc.i4.0
0x1d60c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1d611  ldarg.0
0x1d612  ldstr    aIsprivate// "isprivate"
0x1d617  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d61c  ldarg.3
0x1d61d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_isprivate()
0x1d622  ldc.i4.0
0x1d623  ldc.i4.0
0x1d624  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1d629  ldarg.0
0x1d62a  ldstr    aIsquickfindque// "isquickfindquery"
0x1d62f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d634  ldarg.3
0x1d635  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_isquickfindquery()
0x1d63a  ldc.i4.0
0x1d63b  ldc.i4.0
0x1d63c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1d641  ldarg.0
0x1d642  ldstr    aIsuserdefined// "isuserdefined"
0x1d647  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d64c  ldarg.3
0x1d64d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_isuserdefined()
0x1d652  ldc.i4.0
0x1d653  ldc.i4.0
0x1d654  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1d659  ldarg.0
0x1d65a  ldstr    aLayoutxml// "layoutxml"
0x1d65f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d664  ldarg.3
0x1d665  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_layoutxml()
0x1d66a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d66f  ldarg.0
0x1d670  ldstr    aModifiedby// "modifiedby"
0x1d675  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d67a  ldarg.3
0x1d67b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_modifiedby()
0x1d680  ldc.i4.0
0x1d681  ldc.i4.0
0x1d682  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d687  ldarg.0
0x1d688  ldstr    aModifiedon// "modifiedon"
0x1d68d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d692  ldarg.3
0x1d693  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_modifiedon()
0x1d698  ldc.i4.0
0x1d699  ldc.i4.0
0x1d69a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1d69f  ldarg.0
0x1d6a0  ldstr    aName// "name"
0x1d6a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d6aa  ldarg.3
0x1d6ab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_name()
0x1d6b0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d6b5  ldarg.0
0x1d6b6  ldstr    aOrganizationid// "organizationid"
0x1d6bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d6c0  ldarg.3
0x1d6c1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_organizationid()
0x1d6c6  ldc.i4.0
0x1d6c7  ldc.i4.0
0x1d6c8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1d6cd  ldarg.0
0x1d6ce  ldstr    aQueryapi// "queryapi"
0x1d6d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d6d8  ldarg.3
0x1d6d9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_queryapi()
0x1d6de  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d6e3  ldarg.0
0x1d6e4  ldstr    aQueryappusage// "queryappusage"
0x1d6e9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d6ee  ldarg.3
0x1d6ef  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_queryappusage()
0x1d6f4  ldc.i4.0
0x1d6f5  ldc.i4.0
0x1d6f6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1d6fb  ldarg.0
0x1d6fc  ldstr    aQuerytype// "querytype"
0x1d701  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d706  ldarg.3
0x1d707  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_querytype()
0x1d70c  ldc.i4.0
0x1d70d  ldc.i4.0
0x1d70e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1d713  ldarg.0
0x1d714  ldstr    aReturnedtypeco// "returnedtypecode"
0x1d719  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d71e  ldarg.3
0x1d71f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_returnedtypecode()
0x1d724  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1d729  ldarg.0
0x1d72a  ldstr    aSavedqueryid// "savedqueryid"
0x1d72f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d734  ldarg.3
0x1d735  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_savedqueryid()
0x1d73a  ldc.i4.0
0x1d73b  ldc.i4.0
0x1d73c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1d741  ldarg.0
0x1d742  ldstr    aSavedqueryidun// "savedqueryidunique"
0x1d747  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1d74c  ldarg.3
0x1d74d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.savedquery::get_savedqueryidunique()
0x1d752  ldc.i4.0
0x1d753  ldc.i4.0
0x1d754  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1d759  ldarg.0
0x1d75a  ldarg.3
0x1d75b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1d760  ret
```
