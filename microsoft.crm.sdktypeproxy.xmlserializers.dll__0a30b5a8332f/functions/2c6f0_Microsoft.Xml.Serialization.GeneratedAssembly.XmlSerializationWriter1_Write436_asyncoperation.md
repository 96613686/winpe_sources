# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write436_asyncoperation

- ea: `0x2c6f0`
- end: `0x2ca67`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write436_asyncoperation`
- size: `887`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37e80`
- `0x573f0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x167c0`
- `0x16a10`
- `0x16cb0`
- `0x2c6f0`
- `0x2ca70`

## string_xrefs

- `0x2c735`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c745`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c75d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c775`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c78d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c7a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c7bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c7d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c7eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c801`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c819`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c831`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c847`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c85f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c875`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c88b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c8a3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c8bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c8d1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c8e9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c901`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c919`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c931`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c949`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c95f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c977`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c98f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c9a7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c9bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c9d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c9ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ca07`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ca1f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ca37`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ca4f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2c7a0`: `createdby`
- `0x2c7b8`: `createdon`
- `0x2c758`: `completedon`
- `0x2c788`: `correlationupdatedtime`
- `0x2c7e6`: `dependencytoken`

## pseudocode

```c

```

## disassembly

```asm
0x2c6f0  ldarg.3
0x2c6f1  brtrue.s loc_2C700
0x2c6f3  ldarg.s  4
0x2c6f5  brfalse.s loc_2C6FF
0x2c6f7  ldarg.0
0x2c6f8  ldarg.1
0x2c6f9  ldarg.2
0x2c6fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2c6ff  ret
0x2c700  ldarg.s  5
0x2c702  brtrue.s loc_2C720
0x2c704  ldarg.3
0x2c705  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2c70a  stloc.0
0x2c70b  ldloc.0
0x2c70c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation
0x2c711  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c716  beq.s    loc_2C720
0x2c718  ldarg.0
0x2c719  ldarg.3
0x2c71a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2c71f  throw
0x2c720  ldarg.0
0x2c721  ldarg.1
0x2c722  ldarg.2
0x2c723  ldarg.3
0x2c724  ldc.i4.0
0x2c725  ldnull
0x2c726  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2c72b  ldarg.s  5
0x2c72d  brfalse.s loc_2C73F
0x2c72f  ldarg.0
0x2c730  ldstr    aAsyncoperation_0// "asyncoperation"
0x2c735  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c73a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2c73f  ldarg.0
0x2c740  ldstr    aAsyncoperation_1// "asyncoperationid"
0x2c745  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c74a  ldarg.3
0x2c74b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_asyncoperationid()
0x2c750  ldc.i4.0
0x2c751  ldc.i4.0
0x2c752  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2c757  ldarg.0
0x2c758  ldstr    aCompletedon// "completedon"
0x2c75d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c762  ldarg.3
0x2c763  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_completedon()
0x2c768  ldc.i4.0
0x2c769  ldc.i4.0
0x2c76a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2c76f  ldarg.0
0x2c770  ldstr    aCorrelationid// "correlationid"
0x2c775  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c77a  ldarg.3
0x2c77b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_correlationid()
0x2c780  ldc.i4.0
0x2c781  ldc.i4.0
0x2c782  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x2c787  ldarg.0
0x2c788  ldstr    aCorrelationupd// "correlationupdatedtime"
0x2c78d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c792  ldarg.3
0x2c793  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_correlationupdatedtime()
0x2c798  ldc.i4.0
0x2c799  ldc.i4.0
0x2c79a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2c79f  ldarg.0
0x2c7a0  ldstr    aCreatedby// "createdby"
0x2c7a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c7aa  ldarg.3
0x2c7ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_createdby()
0x2c7b0  ldc.i4.0
0x2c7b1  ldc.i4.0
0x2c7b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2c7b7  ldarg.0
0x2c7b8  ldstr    aCreatedon// "createdon"
0x2c7bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c7c2  ldarg.3
0x2c7c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_createdon()
0x2c7c8  ldc.i4.0
0x2c7c9  ldc.i4.0
0x2c7ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2c7cf  ldarg.0
0x2c7d0  ldstr    aData_0// "data"
0x2c7d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c7da  ldarg.3
0x2c7db  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_data()
0x2c7e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c7e5  ldarg.0
0x2c7e6  ldstr    aDependencytoke// "dependencytoken"
0x2c7eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c7f0  ldarg.3
0x2c7f1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_dependencytoken()
0x2c7f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c7fb  ldarg.0
0x2c7fc  ldstr    aDepth_0// "depth"
0x2c801  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c806  ldarg.3
0x2c807  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_depth()
0x2c80c  ldc.i4.0
0x2c80d  ldc.i4.0
0x2c80e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2c813  ldarg.0
0x2c814  ldstr    aErrorcode_0// "errorcode"
0x2c819  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c81e  ldarg.3
0x2c81f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_errorcode()
0x2c824  ldc.i4.0
0x2c825  ldc.i4.0
0x2c826  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2c82b  ldarg.0
0x2c82c  ldstr    aHostid// "hostid"
0x2c831  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c836  ldarg.3
0x2c837  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_hostid()
0x2c83c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c841  ldarg.0
0x2c842  ldstr    aIswaitingforev// "iswaitingforevent"
0x2c847  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c84c  ldarg.3
0x2c84d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_iswaitingforevent()
0x2c852  ldc.i4.0
0x2c853  ldc.i4.0
0x2c854  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2c859  ldarg.0
0x2c85a  ldstr    aMessage// "message"
0x2c85f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c864  ldarg.3
0x2c865  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_message()
0x2c86a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c86f  ldarg.0
0x2c870  ldstr    aMessagename_0// "messagename"
0x2c875  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c87a  ldarg.3
0x2c87b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_messagename()
0x2c880  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c885  ldarg.0
0x2c886  ldstr    aModifiedby// "modifiedby"
0x2c88b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c890  ldarg.3
0x2c891  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_modifiedby()
0x2c896  ldc.i4.0
0x2c897  ldc.i4.0
0x2c898  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2c89d  ldarg.0
0x2c89e  ldstr    aModifiedon// "modifiedon"
0x2c8a3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c8a8  ldarg.3
0x2c8a9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_modifiedon()
0x2c8ae  ldc.i4.0
0x2c8af  ldc.i4.0
0x2c8b0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2c8b5  ldarg.0
0x2c8b6  ldstr    aName// "name"
0x2c8bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c8c0  ldarg.3
0x2c8c1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_name()
0x2c8c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c8cb  ldarg.0
0x2c8cc  ldstr    aOperationtype// "operationtype"
0x2c8d1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c8d6  ldarg.3
0x2c8d7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_operationtype()
0x2c8dc  ldc.i4.0
0x2c8dd  ldc.i4.0
0x2c8de  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2c8e3  ldarg.0
0x2c8e4  ldstr    aOwnerid// "ownerid"
0x2c8e9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c8ee  ldarg.3
0x2c8ef  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_ownerid()
0x2c8f4  ldc.i4.0
0x2c8f5  ldc.i4.0
0x2c8f6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x2c8fb  ldarg.0
0x2c8fc  ldstr    aOwningbusiness// "owningbusinessunit"
0x2c901  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c906  ldarg.3
0x2c907  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_owningbusinessunit()
0x2c90c  ldc.i4.0
0x2c90d  ldc.i4.0
0x2c90e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2c913  ldarg.0
0x2c914  ldstr    aPostponeuntil// "postponeuntil"
0x2c919  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c91e  ldarg.3
0x2c91f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_postponeuntil()
0x2c924  ldc.i4.0
0x2c925  ldc.i4.0
0x2c926  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2c92b  ldarg.0
0x2c92c  ldstr    aPrimaryentityt// "primaryentitytype"
0x2c931  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c936  ldarg.3
0x2c937  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_primaryentitytype()
0x2c93c  ldc.i4.0
0x2c93d  ldc.i4.0
0x2c93e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x2c943  ldarg.0
0x2c944  ldstr    aRecurrencepatt// "recurrencepattern"
0x2c949  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c94e  ldarg.3
0x2c94f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_recurrencepattern()
0x2c954  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2c959  ldarg.0
0x2c95a  ldstr    aRecurrencestar// "recurrencestarttime"
0x2c95f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c964  ldarg.3
0x2c965  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_recurrencestarttime()
0x2c96a  ldc.i4.0
0x2c96b  ldc.i4.0
0x2c96c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2c971  ldarg.0
0x2c972  ldstr    aRegardingobjec// "regardingobjectid"
0x2c977  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c97c  ldarg.3
0x2c97d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_regardingobjectid()
0x2c982  ldc.i4.0
0x2c983  ldc.i4.0
0x2c984  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2c989  ldarg.0
0x2c98a  ldstr    aRequestid// "requestid"
0x2c98f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c994  ldarg.3
0x2c995  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_requestid()
0x2c99a  ldc.i4.0
0x2c99b  ldc.i4.0
0x2c99c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x2c9a1  ldarg.0
0x2c9a2  ldstr    aRetrycount// "retrycount"
0x2c9a7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c9ac  ldarg.3
0x2c9ad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_retrycount()
0x2c9b2  ldc.i4.0
0x2c9b3  ldc.i4.0
0x2c9b4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2c9b9  ldarg.0
0x2c9ba  ldstr    aStartedon// "startedon"
0x2c9bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c9c4  ldarg.3
0x2c9c5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_startedon()
0x2c9ca  ldc.i4.0
0x2c9cb  ldc.i4.0
0x2c9cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2c9d1  ldarg.0
0x2c9d2  ldstr    aStatecode// "statecode"
0x2c9d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c9dc  ldarg.3
0x2c9dd  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.AsyncOperationStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_statecode()
0x2c9e2  ldc.i4.0
0x2c9e3  ldc.i4.0
0x2c9e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write435_AsyncOperationStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.AsyncOperationStateInfo o, bool isNullable, bool needType)
0x2c9e9  ldarg.0
0x2c9ea  ldstr    aStatuscode// "statuscode"
0x2c9ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2c9f4  ldarg.3
0x2c9f5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_statuscode()
0x2c9fa  ldc.i4.0
0x2c9fb  ldc.i4.0
0x2c9fc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x2ca01  ldarg.0
0x2ca02  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x2ca07  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ca0c  ldarg.3
0x2ca0d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_timezoneruleversionnumber()
0x2ca12  ldc.i4.0
0x2ca13  ldc.i4.0
0x2ca14  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2ca19  ldarg.0
0x2ca1a  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x2ca1f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ca24  ldarg.3
0x2ca25  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_utcconversiontimezonecode()
0x2ca2a  ldc.i4.0
0x2ca2b  ldc.i4.0
0x2ca2c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2ca31  ldarg.0
0x2ca32  ldstr    aWorkflowactiva// "workflowactivationid"
0x2ca37  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ca3c  ldarg.3
0x2ca3d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_workflowactivationid()
0x2ca42  ldc.i4.0
0x2ca43  ldc.i4.0
0x2ca44  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2ca49  ldarg.0
0x2ca4a  ldstr    aWorkflowstagen// "workflowstagename"
0x2ca4f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ca54  ldarg.3
0x2ca55  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.asyncoperation::get_workflowstagename()
0x2ca5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ca5f  ldarg.0
0x2ca60  ldarg.3
0x2ca61  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2ca66  ret
```
