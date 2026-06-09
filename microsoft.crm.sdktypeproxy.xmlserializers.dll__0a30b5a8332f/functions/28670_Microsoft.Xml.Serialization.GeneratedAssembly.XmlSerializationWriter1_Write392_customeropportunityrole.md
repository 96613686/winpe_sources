# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write392_customeropportunityrole

- ea: `0x28670`
- end: `0x2882d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write392_customeropportunityrole`
- size: `445`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37860`
- `0x56c80`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x16a10`
- `0x170c0`
- `0x28670`

## string_xrefs

- `0x286b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x286c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x286dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x286f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2870d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28725`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2873b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28753`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2876b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28783`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2879b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x287b3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x287cb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x287e3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x287fb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28813`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x286c0`: `createdby`
- `0x286d8`: `createdon`
- `0x287de`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x28670  ldarg.3
0x28671  brtrue.s loc_28680
0x28673  ldarg.s  4
0x28675  brfalse.s loc_2867F
0x28677  ldarg.0
0x28678  ldarg.1
0x28679  ldarg.2
0x2867a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2867f  ret
0x28680  ldarg.s  5
0x28682  brtrue.s loc_286A0
0x28684  ldarg.3
0x28685  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2868a  stloc.0
0x2868b  ldloc.0
0x2868c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole
0x28691  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x28696  beq.s    loc_286A0
0x28698  ldarg.0
0x28699  ldarg.3
0x2869a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2869f  throw
0x286a0  ldarg.0
0x286a1  ldarg.1
0x286a2  ldarg.2
0x286a3  ldarg.3
0x286a4  ldc.i4.0
0x286a5  ldnull
0x286a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x286ab  ldarg.s  5
0x286ad  brfalse.s loc_286BF
0x286af  ldarg.0
0x286b0  ldstr    aCustomeropport// "customeropportunityrole"
0x286b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x286ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x286bf  ldarg.0
0x286c0  ldstr    aCreatedby// "createdby"
0x286c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x286ca  ldarg.3
0x286cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_createdby()
0x286d0  ldc.i4.0
0x286d1  ldc.i4.0
0x286d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x286d7  ldarg.0
0x286d8  ldstr    aCreatedon// "createdon"
0x286dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x286e2  ldarg.3
0x286e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_createdon()
0x286e8  ldc.i4.0
0x286e9  ldc.i4.0
0x286ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x286ef  ldarg.0
0x286f0  ldstr    aCustomerid// "customerid"
0x286f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x286fa  ldarg.3
0x286fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_customerid()
0x28700  ldc.i4.0
0x28701  ldc.i4.0
0x28702  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write124_Customer(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer o, bool isNullable, bool needType)
0x28707  ldarg.0
0x28708  ldstr    aCustomeropport_0// "customeropportunityroleid"
0x2870d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28712  ldarg.3
0x28713  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_customeropportunityroleid()
0x28718  ldc.i4.0
0x28719  ldc.i4.0
0x2871a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2871f  ldarg.0
0x28720  ldstr    aDescription_0// "description"
0x28725  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2872a  ldarg.3
0x2872b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_description()
0x28730  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28735  ldarg.0
0x28736  ldstr    aImportsequence// "importsequencenumber"
0x2873b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28740  ldarg.3
0x28741  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_importsequencenumber()
0x28746  ldc.i4.0
0x28747  ldc.i4.0
0x28748  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2874d  ldarg.0
0x2874e  ldstr    aModifiedby// "modifiedby"
0x28753  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28758  ldarg.3
0x28759  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_modifiedby()
0x2875e  ldc.i4.0
0x2875f  ldc.i4.0
0x28760  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28765  ldarg.0
0x28766  ldstr    aModifiedon// "modifiedon"
0x2876b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28770  ldarg.3
0x28771  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_modifiedon()
0x28776  ldc.i4.0
0x28777  ldc.i4.0
0x28778  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2877d  ldarg.0
0x2877e  ldstr    aOpportunityid// "opportunityid"
0x28783  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28788  ldarg.3
0x28789  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_opportunityid()
0x2878e  ldc.i4.0
0x2878f  ldc.i4.0
0x28790  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28795  ldarg.0
0x28796  ldstr    aOpportunityrol// "opportunityroleid"
0x2879b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x287a0  ldarg.3
0x287a1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_opportunityroleid()
0x287a6  ldc.i4.0
0x287a7  ldc.i4.0
0x287a8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x287ad  ldarg.0
0x287ae  ldstr    aOpportunitysta_0// "opportunitystatecode"
0x287b3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x287b8  ldarg.3
0x287b9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_opportunitystatecode()
0x287be  ldc.i4.0
0x287bf  ldc.i4.0
0x287c0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x287c5  ldarg.0
0x287c6  ldstr    aOpportunitysta_2// "opportunitystatuscode"
0x287cb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x287d0  ldarg.3
0x287d1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_opportunitystatuscode()
0x287d6  ldc.i4.0
0x287d7  ldc.i4.0
0x287d8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x287dd  ldarg.0
0x287de  ldstr    aOverriddencrea// "overriddencreatedon"
0x287e3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x287e8  ldarg.3
0x287e9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_overriddencreatedon()
0x287ee  ldc.i4.0
0x287ef  ldc.i4.0
0x287f0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x287f5  ldarg.0
0x287f6  ldstr    aOwnerid// "ownerid"
0x287fb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28800  ldarg.3
0x28801  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_ownerid()
0x28806  ldc.i4.0
0x28807  ldc.i4.0
0x28808  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2880d  ldarg.0
0x2880e  ldstr    aOwningbusiness// "owningbusinessunit"
0x28813  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28818  ldarg.3
0x28819  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeropportunityrole::get_owningbusinessunit()
0x2881e  ldc.i4.0
0x2881f  ldc.i4.0
0x28820  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28825  ldarg.0
0x28826  ldarg.3
0x28827  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2882c  ret
```
