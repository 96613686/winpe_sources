# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write454_workflowlog

- ea: `0x2e260`
- end: `0x2e445`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write454_workflowlog`
- size: `485`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x38190`
- `0x55630`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x2e260`

## string_xrefs

- `0x2e2a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e2b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e2cb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e2e3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e2fb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e313`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e32b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e341`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e359`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e36f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e387`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e39f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e3b7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e3cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e3e7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e3fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e415`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e42b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e2f6`: `createdby`
- `0x2e30e`: `createdon`
- `0x2e2de`: `completedon`

## pseudocode

```c

```

## disassembly

```asm
0x2e260  ldarg.3
0x2e261  brtrue.s loc_2E270
0x2e263  ldarg.s  4
0x2e265  brfalse.s loc_2E26F
0x2e267  ldarg.0
0x2e268  ldarg.1
0x2e269  ldarg.2
0x2e26a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2e26f  ret
0x2e270  ldarg.s  5
0x2e272  brtrue.s loc_2E290
0x2e274  ldarg.3
0x2e275  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2e27a  stloc.0
0x2e27b  ldloc.0
0x2e27c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog
0x2e281  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e286  beq.s    loc_2E290
0x2e288  ldarg.0
0x2e289  ldarg.3
0x2e28a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2e28f  throw
0x2e290  ldarg.0
0x2e291  ldarg.1
0x2e292  ldarg.2
0x2e293  ldarg.3
0x2e294  ldc.i4.0
0x2e295  ldnull
0x2e296  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2e29b  ldarg.s  5
0x2e29d  brfalse.s loc_2E2AF
0x2e29f  ldarg.0
0x2e2a0  ldstr    aWorkflowlog// "workflowlog"
0x2e2a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e2aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2e2af  ldarg.0
0x2e2b0  ldstr    aActivityname// "activityname"
0x2e2b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e2ba  ldarg.3
0x2e2bb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_activityname()
0x2e2c0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e2c5  ldarg.0
0x2e2c6  ldstr    aAsyncoperation_1// "asyncoperationid"
0x2e2cb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e2d0  ldarg.3
0x2e2d1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_asyncoperationid()
0x2e2d6  ldc.i4.0
0x2e2d7  ldc.i4.0
0x2e2d8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e2dd  ldarg.0
0x2e2de  ldstr    aCompletedon// "completedon"
0x2e2e3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e2e8  ldarg.3
0x2e2e9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_completedon()
0x2e2ee  ldc.i4.0
0x2e2ef  ldc.i4.0
0x2e2f0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e2f5  ldarg.0
0x2e2f6  ldstr    aCreatedby// "createdby"
0x2e2fb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e300  ldarg.3
0x2e301  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_createdby()
0x2e306  ldc.i4.0
0x2e307  ldc.i4.0
0x2e308  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e30d  ldarg.0
0x2e30e  ldstr    aCreatedon// "createdon"
0x2e313  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e318  ldarg.3
0x2e319  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_createdon()
0x2e31e  ldc.i4.0
0x2e31f  ldc.i4.0
0x2e320  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e325  ldarg.0
0x2e326  ldstr    aDescription_0// "description"
0x2e32b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e330  ldarg.3
0x2e331  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_description()
0x2e336  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e33b  ldarg.0
0x2e33c  ldstr    aErrorcode_0// "errorcode"
0x2e341  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e346  ldarg.3
0x2e347  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_errorcode()
0x2e34c  ldc.i4.0
0x2e34d  ldc.i4.0
0x2e34e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2e353  ldarg.0
0x2e354  ldstr    aMessage// "message"
0x2e359  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e35e  ldarg.3
0x2e35f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_message()
0x2e364  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e369  ldarg.0
0x2e36a  ldstr    aModifiedby// "modifiedby"
0x2e36f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e374  ldarg.3
0x2e375  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_modifiedby()
0x2e37a  ldc.i4.0
0x2e37b  ldc.i4.0
0x2e37c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e381  ldarg.0
0x2e382  ldstr    aModifiedon// "modifiedon"
0x2e387  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e38c  ldarg.3
0x2e38d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_modifiedon()
0x2e392  ldc.i4.0
0x2e393  ldc.i4.0
0x2e394  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e399  ldarg.0
0x2e39a  ldstr    aOwningbusiness// "owningbusinessunit"
0x2e39f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e3a4  ldarg.3
0x2e3a5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_owningbusinessunit()
0x2e3aa  ldc.i4.0
0x2e3ab  ldc.i4.0
0x2e3ac  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x2e3b1  ldarg.0
0x2e3b2  ldstr    aOwninguser// "owninguser"
0x2e3b7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e3bc  ldarg.3
0x2e3bd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_owninguser()
0x2e3c2  ldc.i4.0
0x2e3c3  ldc.i4.0
0x2e3c4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x2e3c9  ldarg.0
0x2e3ca  ldstr    aRegardingobjec// "regardingobjectid"
0x2e3cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e3d4  ldarg.3
0x2e3d5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_regardingobjectid()
0x2e3da  ldc.i4.0
0x2e3db  ldc.i4.0
0x2e3dc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e3e1  ldarg.0
0x2e3e2  ldstr    aStagename// "stagename"
0x2e3e7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e3ec  ldarg.3
0x2e3ed  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_stagename()
0x2e3f2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e3f7  ldarg.0
0x2e3f8  ldstr    aStatus_0// "status"
0x2e3fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e402  ldarg.3
0x2e403  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_status()
0x2e408  ldc.i4.0
0x2e409  ldc.i4.0
0x2e40a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2e40f  ldarg.0
0x2e410  ldstr    aStepname// "stepname"
0x2e415  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e41a  ldarg.3
0x2e41b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_stepname()
0x2e420  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2e425  ldarg.0
0x2e426  ldstr    aWorkflowlogid// "workflowlogid"
0x2e42b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e430  ldarg.3
0x2e431  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.workflowlog::get_workflowlogid()
0x2e436  ldc.i4.0
0x2e437  ldc.i4.0
0x2e438  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2e43d  ldarg.0
0x2e43e  ldarg.3
0x2e43f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2e444  ret
```
