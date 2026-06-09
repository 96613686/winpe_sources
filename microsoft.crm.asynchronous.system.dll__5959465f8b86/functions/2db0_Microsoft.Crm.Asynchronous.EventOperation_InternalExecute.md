# Microsoft.Crm.Asynchronous.EventOperation::InternalExecute

- ea: `0x2db0`
- end: `0x2f8e`
- name: `Microsoft.Crm.Asynchronous.EventOperation::InternalExecute`
- size: `478`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2b40`
- `0x2bd0`
- `0x2c30`
- `0x2c60`
- `0x2d80`
- `0x2db0`
- `0x2f90`
- `0x3170`
- `0x31b0`
- `0x3280`
- `0x33e0`
- `0x3450`

## string_xrefs

- `0x2dfa`: `Could not find the plugin assembly or type to execute.`

## pseudocode

```c

```

## disassembly

```asm
0x2db0  ldarg.1
0x2db1  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x2db6  ldc.i4.1
0x2db7  ceq
0x2db9  ldstr    aOperationTypeM_9// "Operation type must be 'Event'"
0x2dbe  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2dc3  ldarg.1
0x2dc4  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0x2dc9  ldc.i4.1
0x2dca  bne.un.s loc_2DD2
0x2dcc  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0x2dd1  ret
0x2dd2  ldarg.0
0x2dd3  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_AsyncService()
0x2dd8  ldarg.1
0x2dd9  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent)
0x2dde  stloc.0
0x2ddf  ldarg.0
0x2de0  ldloc.0
0x2de1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData Microsoft.Crm.Asynchronous.EventOperation::GetPluginAssembly(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x2de6  stloc.1
0x2de7  ldarg.0
0x2de8  ldloc.0
0x2de9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData Microsoft.Crm.Asynchronous.EventOperation::GetPluginType(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x2dee  stloc.2
0x2def  ldloc.1
0x2df0  brfalse.s loc_2DF5
0x2df2  ldloc.2
0x2df3  brtrue.s loc_2E11
0x2df5  ldc.i4   0x80040216
0x2dfa  ldstr    aCouldNotFindTh// "Could not find the plugin assembly or t"...
0x2dff  ldc.i4.0
0x2e00  newarr   [mscorlib]System.Object
0x2e05  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0x2e0a  stloc.s  6
0x2e0c  leave    loc_2F8B
0x2e11  ldarg.0
0x2e12  ldloc.1
0x2e13  ldloc.2
0x2e14  call     instance bool Microsoft.Crm.Asynchronous.EventOperation::SkipOnBackgroundProcessingDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData assemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData typeData)
0x2e19  brfalse.s loc_2E37
0x2e1b  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MaxValue()
0x2e20  ldarg.1
0x2e21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2e26  call     string Microsoft.Crm.Asynchronous.EventOperation::GetAsyncOperationSkippedMessage(valuetype [mscorlib]System.Guid organizationId)
0x2e2b  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor(valuetype [mscorlib]System.DateTime, string)
0x2e30  stloc.s  6
0x2e32  leave    loc_2F8B
0x2e37  nop
0x2e38  ldarg.0
0x2e39  ldloc.1
0x2e3a  call     instance void Microsoft.Crm.Asynchronous.EventOperation::VerifyAllowedToRun(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData pluginAssemblyData)
0x2e3f  leave.s  loc_2E63
0x2e41  stloc.s  7
0x2e43  ldloc.s  7
0x2e45  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x2e4a  ldloc.s  7
0x2e4c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2e51  ldc.i4.0
0x2e52  newarr   [mscorlib]System.Object
0x2e57  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0x2e5c  stloc.s  6
0x2e5e  leave    loc_2F8B
0x2e63  ldnull
0x2e64  stloc.3
0x2e65  ldc.i4.1
0x2e66  stloc.s  4
0x2e68  ldloc.2
0x2e69  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_IsolationMode()
0x2e6e  ldc.i4.2
0x2e6f  beq.s    loc_2E7A
0x2e71  ldloc.2
0x2e72  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_SourceType()
0x2e77  ldc.i4.3
0x2e78  bne.un.s loc_2EF5
0x2e7a  ldloc.2
0x2e7b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_IsolationMode()
0x2e80  ldc.i4.2
0x2e81  bne.un.s loc_2EE2
0x2e83  ldloc.0
0x2e84  call     string Microsoft.Crm.Asynchronous.EventOperation::GetStepConfiguration(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x2e89  stloc.s  8
0x2e8b  ldloc.0
0x2e8c  call     string Microsoft.Crm.Asynchronous.EventOperation::GetStepSecureConfiguration(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x2e91  stloc.s  9
0x2e93  ldarg.0
0x2e94  ldloc.0
0x2e95  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EventOperation::GetPluginTypeId(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x2e9a  stloc.s  0xA
0x2e9c  newobj   instance void [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::.ctor()
0x2ea1  dup
0x2ea2  ldloc.s  0xA
0x2ea4  stfld    valuetype [mscorlib]System.Guid [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::pluginTypeId
0x2ea9  dup
0x2eaa  ldloc.2
0x2eab  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::pluginTypeData
0x2eb0  dup
0x2eb1  ldloc.1
0x2eb2  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::pluginAssemblyData
0x2eb7  dup
0x2eb8  ldloc.0
0x2eb9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OrganizationId()
0x2ebe  stfld    valuetype [mscorlib]System.Guid [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::orgId
0x2ec3  dup
0x2ec4  ldloc.s  8
0x2ec6  stfld    string [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::stepDescriptionConfiguration
0x2ecb  dup
0x2ecc  ldloc.s  9
0x2ece  stfld    string [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::stepDescriptionSecureConfiguration
0x2ed3  dup
0x2ed4  ldc.i4.0
0x2ed5  stfld    valuetype [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemoteCodeUnitType [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::remoteCodeUnitType
0x2eda  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactory::CreateRemotePlugin(class [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest)
0x2edf  stloc.3
0x2ee0  br.s     loc_2F2F
0x2ee2  ldc.i4   0x80050241
0x2ee7  ldc.i4.s 0x41
0x2ee9  ldc.i4.0
0x2eea  newarr   [mscorlib]System.Object
0x2eef  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, object[])
0x2ef4  throw
0x2ef5  ldloc.2
0x2ef6  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.GenericSharedOrganizationData`1<class [mscorlib]System.Type>::get_Value()
0x2efb  stloc.s  0xB
0x2efd  ldloc.s  0xB
0x2eff  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x2f04  call     void [Microsoft.Crm]Microsoft.Crm.Extensibility.PluginAssemblyFactory::VerifyPublicKeyToken(class [mscorlib]System.Reflection.Assembly)
0x2f09  ldloc.1
0x2f0a  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData::get_PluginAssemblyTargetVersion()
0x2f0f  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x2f14  ldc.i4.4
0x2f15  bne.un.s loc_2F24
0x2f17  ldloc.s  0xB
0x2f19  ldloc.0
0x2f1a  ldloca.s 4
0x2f1c  newobj   instance void Microsoft.Crm.Asynchronous.V4ProxyPlugin::.ctor(class [mscorlib]System.Type pluginType, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context, [out] bool& isValid)
0x2f21  stloc.3
0x2f22  br.s     loc_2F2F
0x2f24  ldloc.s  0xB
0x2f26  ldloc.0
0x2f27  ldloca.s 4
0x2f29  newobj   instance void Microsoft.Crm.Asynchronous.V5ProxyPlugin::.ctor(class [mscorlib]System.Type type, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context, [out] bool& isValid)
0x2f2e  stloc.3
0x2f2f  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x2f34  ldarg.1
0x2f35  ldloc.2
0x2f36  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogEventOperationData(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData)
0x2f3b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2f40  ldstr    aType0DoesNotIm// "Type '{0}' does not implement required "...
0x2f45  ldc.i4.1
0x2f46  newarr   [mscorlib]System.Object
0x2f4b  dup
0x2f4c  ldc.i4.0
0x2f4d  ldloc.2
0x2f4e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_PluginTypeName()
0x2f53  stelem.ref
0x2f54  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2f59  stloc.s  5
0x2f5b  ldloc.s  4
0x2f5d  brtrue.s loc_2F75
0x2f5f  ldc.i4   0x8004A200
0x2f64  ldloc.s  5
0x2f66  ldc.i4.0
0x2f67  newarr   [mscorlib]System.Object
0x2f6c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0x2f71  stloc.s  6
0x2f73  leave.s  loc_2F8B
0x2f75  ldarg.0
0x2f76  ldloc.0
0x2f77  ldloc.3
0x2f78  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.EventOperation::InvokePlugin(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin pluginInstance)
0x2f7d  stloc.s  6
0x2f7f  leave.s  loc_2F8B
0x2f81  ldloc.0
0x2f82  brfalse.s loc_2F8A
0x2f84  ldloc.0
0x2f85  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f8a  endfinally
0x2f8b  ldloc.s  6
0x2f8d  ret
```
