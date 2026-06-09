# Microsoft.Crm.Sandbox.PluginTraceLogWriter::CreateInitial

- ea: `0x6a80`
- end: `0x6cda`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogWriter::CreateInitial`
- size: `602`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## string_xrefs

- `0x6a97`: `PluginTraceLogWriter.CreateInitial: enter`
- `0x6abd`: `PluginTraceLogDbWriteTimeoutInSeconds`
- `0x6ad3`: `plugintracelogid`
- `0x6aee`: `configuration`
- `0x6c3b`: `secureconfiguration`
- `0x6c67`: `pluginstepid`
- `0x6cc9`: `issystemcreated`

## pseudocode

```c

```

## disassembly

```asm
0x6a80  ldarg.0
0x6a81  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6a86  ldstr    aPtlr// "_ptlr"
0x6a8b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6a90  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6a95  ldc.i4.s 0x28
0x6a97  ldstr    aPlugintracelog_14// "PluginTraceLogWriter.CreateInitial: ent"...
0x6a9c  ldc.i4.0
0x6a9d  newarr   [mscorlib]System.Object
0x6aa2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6aa7  ldc.i4   0x120B
0x6aac  ldarg.0
0x6aad  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6ab2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x6ab7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(int32, valuetype [mscorlib]System.Guid)
0x6abc  dup
0x6abd  ldstr    aPlugintracelog_15// "PluginTraceLogDbWriteTimeoutInSeconds"
0x6ac2  ldc.i4.5
0x6ac3  call     T0x2B000002
0x6ac8  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x6acd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_CreateTimeout(valuetype [mscorlib]System.Nullable`1<int32>)
0x6ad2  dup
0x6ad3  ldstr    aPlugintracelog_16// "plugintracelogid"
0x6ad8  ldarg.0
0x6ad9  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6ade  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_PluginTraceLogId()
0x6ae3  box      [mscorlib]System.Guid
0x6ae8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6aed  dup
0x6aee  ldstr    aConfiguration// "configuration"
0x6af3  ldarg.0
0x6af4  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6af9  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_Configuration()
0x6afe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6b03  dup
0x6b04  ldstr    aMessagename_0// "messagename"
0x6b09  ldarg.0
0x6b0a  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6b0f  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_MessageName()
0x6b14  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6b19  dup
0x6b1a  ldstr    aDepth// "depth"
0x6b1f  ldarg.0
0x6b20  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6b25  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_Depth()
0x6b2a  box      [mscorlib]System.Int32
0x6b2f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6b34  dup
0x6b35  ldstr    aMode// "mode"
0x6b3a  ldarg.0
0x6b3b  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6b40  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_Mode()
0x6b45  box      [mscorlib]System.Int32
0x6b4a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6b4f  dup
0x6b50  ldstr    aOperationtype// "operationtype"
0x6b55  ldarg.0
0x6b56  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6b5b  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OperationType()
0x6b60  box      [mscorlib]System.Int32
0x6b65  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6b6a  dup
0x6b6b  ldstr    aPerformanceexe// "performanceexecutionstarttime"
0x6b70  ldarg.0
0x6b71  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6b76  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_PerformanceExecutionStartTime()
0x6b7b  ldc.i4.1
0x6b7c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x6b81  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6b86  dup
0x6b87  ldstr    aPerformancecon// "performanceconstructorstarttime"
0x6b8c  ldarg.0
0x6b8d  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6b92  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_PerformanceConstructorStartTime()
0x6b97  ldc.i4.1
0x6b98  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x6b9d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6ba2  dup
0x6ba3  ldstr    aPerformanceexe_0// "performanceexecutionduration"
0x6ba8  ldarg.0
0x6ba9  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6bae  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_PerformanceExecutionDuration()
0x6bb3  box      [mscorlib]System.Int32
0x6bb8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6bbd  dup
0x6bbe  ldstr    aPerformancecon_0// "performanceconstructorduration"
0x6bc3  ldarg.0
0x6bc4  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6bc9  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_PerformanceConstructorDuration()
0x6bce  box      [mscorlib]System.Int32
0x6bd3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6bd8  dup
0x6bd9  ldstr    aPersistencekey// "persistencekey"
0x6bde  ldarg.0
0x6bdf  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6be4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_PersistenceKey()
0x6be9  box      [mscorlib]System.Guid
0x6bee  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6bf3  dup
0x6bf4  ldstr    aPrimaryentity// "primaryentity"
0x6bf9  ldarg.0
0x6bfa  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6bff  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_PrimaryEntity()
0x6c04  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6c09  dup
0x6c0a  ldstr    aProfile// "profile"
0x6c0f  ldarg.0
0x6c10  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6c15  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_Profile()
0x6c1a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6c1f  dup
0x6c20  ldstr    aRequestid_0// "requestid"
0x6c25  ldarg.0
0x6c26  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6c2b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_RequestId()
0x6c30  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x6c35  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6c3a  dup
0x6c3b  ldstr    aSecureconfigur// "secureconfiguration"
0x6c40  ldarg.0
0x6c41  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6c46  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_SecureConfiguration()
0x6c4b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6c50  dup
0x6c51  ldstr    aTypename_0// "typename"
0x6c56  ldarg.0
0x6c57  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6c5c  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_PluginTypeName()
0x6c61  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6c66  dup
0x6c67  ldstr    aPluginstepid// "pluginstepid"
0x6c6c  ldarg.0
0x6c6d  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6c72  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_PluginStepId()
0x6c77  box      [mscorlib]System.Guid
0x6c7c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6c81  dup
0x6c82  ldstr    aMessageblock// "messageblock"
0x6c87  ldarg.0
0x6c88  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6c8d  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_TraceText()
0x6c92  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6c97  dup
0x6c98  ldstr    aExceptiondetai_0// "exceptiondetails"
0x6c9d  ldarg.0
0x6c9e  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6ca3  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_ExceptionDetails()
0x6ca8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6cad  dup
0x6cae  ldstr    aCorrelationid// "correlationid"
0x6cb3  ldarg.0
0x6cb4  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord Microsoft.Crm.Sandbox.PluginTraceLogWriter::_ptlr
0x6cb9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_CorrelationId()
0x6cbe  box      [mscorlib]System.Guid
0x6cc3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6cc8  dup
0x6cc9  ldstr    aIssystemcreate// "issystemcreated"
0x6cce  ldc.i4.1
0x6ccf  box      [mscorlib]System.Boolean
0x6cd4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x6cd9  ret
```
