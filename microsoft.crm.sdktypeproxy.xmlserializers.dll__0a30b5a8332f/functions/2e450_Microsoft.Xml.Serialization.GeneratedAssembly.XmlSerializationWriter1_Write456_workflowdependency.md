# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write456_workflowdependency

- ea: `0x2e450`
- end: `0x2e647`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write456_workflowdependency`
- size: `503`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x38200`
- `0x57700`

## callees

- `0x5cf0`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x2e450`

## string_xrefs

- `0x2e495`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e4a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e4bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e4d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e4eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e501`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e517`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e52d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e545`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e55d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e575`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e58d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e5a3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e5b9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e5cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e5e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e5fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e615`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e62d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e4a0`: `createdby`
- `0x2e4b8`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x2e450  ldarg.3
0x2e451  brtrue.s loc_2E460
0x2e453  ldarg.s  4
0x2e455  brfalse.s loc_2E45F
0x2e457  ldarg.0
0x2e458  ldarg.1
0x2e459  ldarg.2
0x2e45a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2e45f  ret
0x2e460  ldarg.s  5
0x2e462  brtrue.s loc_2E480
0x2e464  ldarg.3
0x2e465  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2e46a  stloc.0
0x2e46b  ldloc.0
0x2e46c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency
0x2e471  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e476  beq.s    loc_2E480
0x2e478  ldarg.0
0x2e479  ldarg.3
0x2e47a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2e47f  throw
0x2e480  ldarg.0
0x2e481  ldarg.1
0x2e482  ldarg.2
0x2e483  ldarg.3
0x2e484  ldc.i4.0
0x2e485  ldnull
0x2e486  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2e48b  ldarg.s  5
0x2e48d  brfalse.s loc_2E49F
0x2e48f  ldarg.0
0x2e490  ldstr    aWorkflowdepend// "workflowdependency"
0x2e495  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e49a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2e49f  ldarg.0
0x2e4a0  ldstr    aCreatedby// "createdby"
0x2e4a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e4aa  ldarg.3
0x2e4ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_createdby()
0x2e4b0  ldc.i4.0
0x2e4b1  ldc.i4.0
0x2e4b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e4b7  ldarg.0
0x2e4b8  ldstr    aCreatedon// "createdon"
0x2e4bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e4c2  ldarg.3
0x2e4c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_createdon()
0x2e4c8  ldc.i4.0
0x2e4c9  ldc.i4.0
0x2e4ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e4cf  ldarg.0
0x2e4d0  ldstr    aCustomentityna// "customentityname"
0x2e4d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e4da  ldarg.3
0x2e4db  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_customentityname()
0x2e4e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e4e5  ldarg.0
0x2e4e6  ldstr    aDependentattri// "dependentattributename"
0x2e4eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e4f0  ldarg.3
0x2e4f1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_dependentattributename()
0x2e4f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e4fb  ldarg.0
0x2e4fc  ldstr    aDependententit// "dependententityname"
0x2e501  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e506  ldarg.3
0x2e507  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_dependententityname()
0x2e50c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e511  ldarg.0
0x2e512  ldstr    aEntityattribut// "entityattributes"
0x2e517  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e51c  ldarg.3
0x2e51d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_entityattributes()
0x2e522  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e527  ldarg.0
0x2e528  ldstr    aModifiedby// "modifiedby"
0x2e52d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e532  ldarg.3
0x2e533  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_modifiedby()
0x2e538  ldc.i4.0
0x2e539  ldc.i4.0
0x2e53a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e53f  ldarg.0
0x2e540  ldstr    aModifiedon// "modifiedon"
0x2e545  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e54a  ldarg.3
0x2e54b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_modifiedon()
0x2e550  ldc.i4.0
0x2e551  ldc.i4.0
0x2e552  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e557  ldarg.0
0x2e558  ldstr    aOwningbusiness// "owningbusinessunit"
0x2e55d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e562  ldarg.3
0x2e563  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_owningbusinessunit()
0x2e568  ldc.i4.0
0x2e569  ldc.i4.0
0x2e56a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x2e56f  ldarg.0
0x2e570  ldstr    aOwninguser// "owninguser"
0x2e575  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e57a  ldarg.3
0x2e57b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_owninguser()
0x2e580  ldc.i4.0
0x2e581  ldc.i4.0
0x2e582  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x2e587  ldarg.0
0x2e588  ldstr    aParametername// "parametername"
0x2e58d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e592  ldarg.3
0x2e593  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_parametername()
0x2e598  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e59d  ldarg.0
0x2e59e  ldstr    aParametertype// "parametertype"
0x2e5a3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e5a8  ldarg.3
0x2e5a9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_parametertype()
0x2e5ae  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e5b3  ldarg.0
0x2e5b4  ldstr    aRelatedattribu// "relatedattributename"
0x2e5b9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e5be  ldarg.3
0x2e5bf  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_relatedattributename()
0x2e5c4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e5c9  ldarg.0
0x2e5ca  ldstr    aRelatedentityn// "relatedentityname"
0x2e5cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e5d4  ldarg.3
0x2e5d5  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_relatedentityname()
0x2e5da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e5df  ldarg.0
0x2e5e0  ldstr    aSdkmessageid// "sdkmessageid"
0x2e5e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e5ea  ldarg.3
0x2e5eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_sdkmessageid()
0x2e5f0  ldc.i4.0
0x2e5f1  ldc.i4.0
0x2e5f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e5f7  ldarg.0
0x2e5f8  ldstr    aType_0// "type"
0x2e5fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e602  ldarg.3
0x2e603  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_type()
0x2e608  ldc.i4.0
0x2e609  ldc.i4.0
0x2e60a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2e60f  ldarg.0
0x2e610  ldstr    aWorkflowdepend_0// "workflowdependencyid"
0x2e615  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e61a  ldarg.3
0x2e61b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_workflowdependencyid()
0x2e620  ldc.i4.0
0x2e621  ldc.i4.0
0x2e622  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2e627  ldarg.0
0x2e628  ldstr    aWorkflowid// "workflowid"
0x2e62d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e632  ldarg.3
0x2e633  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowdependency::get_workflowid()
0x2e638  ldc.i4.0
0x2e639  ldc.i4.0
0x2e63a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e63f  ldarg.0
0x2e640  ldarg.3
0x2e641  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2e646  ret
```
