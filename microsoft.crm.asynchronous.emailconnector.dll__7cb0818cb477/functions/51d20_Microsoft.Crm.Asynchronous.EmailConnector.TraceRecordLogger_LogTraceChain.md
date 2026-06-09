# Microsoft.Crm.Asynchronous.EmailConnector.TraceRecordLogger::LogTraceChain

- ea: `0x51d20`
- end: `0x51f21`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.TraceRecordLogger::LogTraceChain`
- size: `513`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x51c60`
- `0x77970`

## callees

- `0x4d8c0`
- `0x4da80`
- `0x51d20`
- `0x51f30`
- `0x51fc0`
- `0x71c20`

## string_xrefs

- `0x51e44`: `Creation of TraceLog failed-\nRegarding Object: ({0}, {1})\nTrace Code: {2}\nTrace Level: {3}\nCollation Level: {4}\nUnique: {5}\nParentTraceLogId: {6}\nTrace Parameter XML: {7}\nException: {8}`
- `0x51eec`: `traceparameterxml`

## pseudocode

```c

```

## disassembly

```asm
0x51d20  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x51d25  stloc.0
0x51d26  ldc.i4.1
0x51d27  stloc.1
0x51d28  ldarg.1
0x51d29  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_OrganizationId()
0x51d2e  stloc.2
0x51d2f  ldarg.0
0x51d30  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x51d35  stloc.3
0x51d36  br       loc_51F09
0x51d3b  ldloc.3
0x51d3c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x51d41  stloc.s  4
0x51d43  ldloc.s  4
0x51d45  ldloc.2
0x51d46  ldarg.2
0x51d47  call     bool Microsoft.Crm.Asynchronous.EmailConnector.TraceRecordLogger::IsValidTrace(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity traceRecord, valuetype [mscorlib]System.Guid organizationId, bool isInTestAccessMode)
0x51d4c  brfalse  loc_51F09
0x51d51  ldloc.1
0x51d52  brfalse.s loc_51D65
0x51d54  ldloc.s  4
0x51d56  ldstr    aParenttracelog// "parenttracelogid"
0x51d5b  ldnull
0x51d5c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x51d61  ldc.i4.0
0x51d62  stloc.1
0x51d63  br.s     loc_51D98
0x51d65  ldloc.0
0x51d66  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x51d6b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x51d70  brfalse.s loc_51D8B
0x51d72  ldloc.s  4
0x51d74  ldstr    aParenttracelog// "parenttracelogid"
0x51d79  ldstr    aTracelog// "tracelog"
0x51d7e  ldloc.0
0x51d7f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x51d84  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x51d89  br.s     loc_51D98
0x51d8b  ldloc.s  4
0x51d8d  ldstr    aParenttracelog// "parenttracelogid"
0x51d92  ldnull
0x51d93  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x51d98  ldloc.2
0x51d99  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x51d9e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x51da3  ldc.i4   0x1F72
0x51da8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x51dad  stloc.s  5
0x51daf  ldloc.s  5
0x51db1  brfalse.s loc_51DC6
0x51db3  ldloc.s  5
0x51db5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x51dba  ldstr    aMachinename_0// "machinename"
0x51dbf  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x51dc4  brtrue.s loc_51DE6
0x51dc6  ldloc.s  4
0x51dc8  ldstr    aMachinename_0// "machinename"
0x51dcd  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x51dd2  brfalse.s loc_51DE6
0x51dd4  ldloc.s  4
0x51dd6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x51ddb  ldstr    aMachinename_0// "machinename"
0x51de0  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Remove(var<u1>)
0x51de5  pop
0x51de6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::.ctor()
0x51deb  stloc.s  6
0x51ded  ldloc.s  6
0x51def  ldloc.s  4
0x51df1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x51df6  ldloc.2
0x51df7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x51dfc  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x51e01  stloc.s  7
0x51e03  ldloc.s  7
0x51e05  ldloc.s  6
0x51e07  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x51e0c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateResponse
0x51e11  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateResponse::get_id()
0x51e16  stloc.0
0x51e17  leave    loc_51F09
0x51e1c  stloc.s  8
0x51e1e  ldloc.s  4
0x51e20  ldstr    aRegardingobjec// "regardingobjectid"
0x51e25  callvirt T0x2B00008E
0x51e2a  stloc.s  9
0x51e2c  ldloc.s  4
0x51e2e  ldstr    aLevel// "level"
0x51e33  callvirt T0x2B00008F
0x51e38  stloc.s  0xA
0x51e3a  ldloc.2
0x51e3b  ldarg.1
0x51e3c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x51e41  ldc.i4.s 0x3D
0x51e43  ldc.i4.2
0x51e44  ldstr    aCreationOfTrac// "Creation of TraceLog failed-\r\nRegardi"...
0x51e49  ldc.i4.s 9
0x51e4b  newarr   [mscorlib]System.Object
0x51e50  dup
0x51e51  ldc.i4.0
0x51e52  ldloc.s  9
0x51e54  brtrue.s loc_51E5D
0x51e56  ldsfld   string [mscorlib]System.String::Empty
0x51e5b  br.s     loc_51E64
0x51e5d  ldloc.s  9
0x51e5f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x51e64  stelem.ref
0x51e65  dup
0x51e66  ldc.i4.1
0x51e67  ldloc.s  9
0x51e69  brtrue.s loc_51E72
0x51e6b  ldsfld   string [mscorlib]System.String::Empty
0x51e70  br.s     loc_51E87
0x51e72  ldloc.s  9
0x51e74  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x51e79  stloc.s  0xB
0x51e7b  ldloca.s 0xB
0x51e7d  ldstr    aD// "D"
0x51e82  call     instance string [mscorlib]System.Guid::ToString(string)
0x51e87  stelem.ref
0x51e88  dup
0x51e89  ldc.i4.2
0x51e8a  ldloc.s  4
0x51e8c  ldstr    aTracecode// "tracecode"
0x51e91  call     object Microsoft.Crm.Asynchronous.EmailConnector.TraceRecordLogger::GetAttributeValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeLogicalName)
0x51e96  stelem.ref
0x51e97  dup
0x51e98  ldc.i4.3
0x51e99  ldloc.s  0xA
0x51e9b  brtrue.s loc_51EA4
0x51e9d  ldsfld   string [mscorlib]System.String::Empty
0x51ea2  br.s     loc_51EB9
0x51ea4  ldloc.s  0xA
0x51ea6  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x51eab  stloc.s  0xC
0x51ead  ldloca.s 0xC
0x51eaf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51eb4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x51eb9  stelem.ref
0x51eba  dup
0x51ebb  ldc.i4.4
0x51ebc  ldloc.s  4
0x51ebe  ldstr    aCollationlevel// "collationlevel"
0x51ec3  call     object Microsoft.Crm.Asynchronous.EmailConnector.TraceRecordLogger::GetAttributeValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeLogicalName)
0x51ec8  stelem.ref
0x51ec9  dup
0x51eca  ldc.i4.5
0x51ecb  ldloc.s  4
0x51ecd  ldstr    aIsunique// "isunique"
0x51ed2  call     object Microsoft.Crm.Asynchronous.EmailConnector.TraceRecordLogger::GetAttributeValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeLogicalName)
0x51ed7  stelem.ref
0x51ed8  dup
0x51ed9  ldc.i4.6
0x51eda  ldloca.s 0
0x51edc  constrained. [mscorlib]System.Guid
0x51ee2  callvirt instance string [mscorlib]System.Object::ToString()
0x51ee7  stelem.ref
0x51ee8  dup
0x51ee9  ldc.i4.7
0x51eea  ldloc.s  4
0x51eec  ldstr    aTraceparameter// "traceparameterxml"
0x51ef1  call     object Microsoft.Crm.Asynchronous.EmailConnector.TraceRecordLogger::GetAttributeValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string attributeLogicalName)
0x51ef6  stelem.ref
0x51ef7  dup
0x51ef8  ldc.i4.8
0x51ef9  ldloc.s  8
0x51efb  ldloc.2
0x51efc  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x51f01  stelem.ref
0x51f02  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x51f07  leave.s  loc_51F09
0x51f09  ldloc.3
0x51f0a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x51f0f  brtrue   loc_51D3B
0x51f14  leave.s  loc_51F20
0x51f16  ldloc.3
0x51f17  brfalse.s loc_51F1F
0x51f19  ldloc.3
0x51f1a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51f1f  endfinally
0x51f20  ret
```
