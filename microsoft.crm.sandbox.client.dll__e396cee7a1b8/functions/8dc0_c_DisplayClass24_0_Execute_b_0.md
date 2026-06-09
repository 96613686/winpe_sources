# <>c__DisplayClass24_0::<Execute>b__0

- ea: `0x8dc0`
- end: `0x911a`
- name: `<>c__DisplayClass24_0::<Execute>b__0`
- size: `858`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0xc0`
- `0xd0`
- `0x480`
- `0x560`
- `0x580`
- `0x23d0`
- `0x2c40`
- `0x30b0`
- `0x33b0`
- `0x8dc0`

## string_xrefs

- `0x8ddb`: `context.OwningExtension`
- `0x8f20`: `SandboxPlugin.Execute: enter`
- `0x8f4e`: `Retriable failure while executing plugin. This can be safely retried on a different host`
- `0x90ec`: `Retriable failure while executing plugin. This can be safely retried on a different host`
- `0x90fb`: `SandboxPlugin.Execute: exit`

## pseudocode

```c

```

## disassembly

```asm
0x8dc0  ldarg.0
0x8dc1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8dc6  ldstr    aContext// "context"
0x8dcb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8dd0  ldarg.0
0x8dd1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8dd6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x8ddb  ldstr    aContextOwninge// "context.OwningExtension"
0x8de0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8de5  ldarg.0
0x8de6  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8deb  brtrue.s loc_8DF4
0x8ded  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8df2  br.s     loc_8DFF
0x8df4  ldarg.0
0x8df5  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8dfa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x8dff  stloc.0
0x8e00  ldarg.0
0x8e01  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8e06  brfalse.s loc_8E1E
0x8e08  ldarg.0
0x8e09  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8e0e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x8e13  stloc.s  5
0x8e15  ldloca.s 5
0x8e17  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x8e1c  brtrue.s loc_8E25
0x8e1e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8e23  br.s     loc_8E39
0x8e25  ldarg.0
0x8e26  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8e2b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x8e30  stloc.s  5
0x8e32  ldloca.s 5
0x8e34  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x8e39  stloc.1
0x8e3a  ldarg.0
0x8e3b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8e40  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x8e45  stloc.2
0x8e46  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8e4b  stloc.3
0x8e4c  ldarg.0
0x8e4d  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8e52  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x8e57  stloc.s  4
0x8e59  ldstr    aSandboxcodeuni_3// "SandboxCodeUnit.Execute"
0x8e5e  ldsfld   string [mscorlib]System.String::Empty
0x8e63  ldloc.s  4
0x8e65  ldloc.1
0x8e66  ldloc.0
0x8e67  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8e6c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_ActivityId()
0x8e71  ldloc.2
0x8e72  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x8e77  stloc.s  6
0x8e79  ldarg.0
0x8e7a  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8e7f  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x8e84  stloc.s  7
0x8e86  ldarg.0
0x8e87  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8e8c  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorkflowContext
0x8e91  stloc.s  8
0x8e93  ldloc.s  7
0x8e95  brfalse.s loc_8ED1
0x8e97  ldloc.s  7
0x8e99  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x8e9e  brfalse.s loc_8ED1
0x8ea0  ldloc.s  7
0x8ea2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x8ea7  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0x8eac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_ParentPluginExecutionId()
0x8eb1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8eb6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8ebb  brfalse.s loc_8ED1
0x8ebd  ldloc.s  7
0x8ebf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x8ec4  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0x8ec9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_ParentPluginExecutionId()
0x8ece  stloc.3
0x8ecf  br.s     loc_8EFF
0x8ed1  ldloc.s  8
0x8ed3  brfalse.s loc_8EF2
0x8ed5  ldloc.s  8
0x8ed7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorkflowContext::get_ParentPluginExecutionId()
0x8edc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8ee1  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8ee6  brfalse.s loc_8EF2
0x8ee8  ldloc.s  8
0x8eea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorkflowContext::get_ParentPluginExecutionId()
0x8eef  stloc.3
0x8ef0  br.s     loc_8EFF
0x8ef2  ldarg.0
0x8ef3  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8ef8  ldloca.s 3
0x8efa  call     void Microsoft.Crm.Sandbox.SandboxCodeUnit::GetAsyncParentPluginExecutionId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, [out] valuetype [mscorlib]System.Guid& parentPluginExecutionId)
0x8eff  ldarg.0
0x8f00  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x8f05  call     instance void Microsoft.Crm.Sandbox.SandboxCodeUnit::EnsureListenerStarted()
0x8f0a  ldnull
0x8f0b  stloc.s  9
0x8f0d  ldc.i4.0
0x8f0e  stloc.s  0xA
0x8f10  ldnull
0x8f11  stloc.s  0xB
0x8f13  ldnull
0x8f14  stloc.s  0xC
0x8f16  ldnull
0x8f17  stloc.s  0xD
0x8f19  ldnull
0x8f1a  stloc.s  0xE
0x8f1c  ldloc.s  4
0x8f1e  ldc.i4.s 0x21
0x8f20  ldstr    aSandboxpluginE_9// "SandboxPlugin.Execute: enter"
0x8f25  ldc.i4.0
0x8f26  newarr   [mscorlib]System.Object
0x8f2b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8f30  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x8f35  stloc.s  0xF
0x8f37  ldc.i4.0
0x8f38  stloc.s  0x10
0x8f3a  br       loc_90D2
0x8f3f  ldarg.0
0x8f40  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x8f45  ldfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x8f4a  brtrue.s loc_8F59
0x8f4c  ldloc.s  0xE
0x8f4e  ldstr    aRetriableFailu// "Retriable failure while executing plugi"...
0x8f53  newobj   instance void [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginRetriableException::.ctor(class [mscorlib]System.Exception, string)
0x8f58  throw
0x8f59  call     class Microsoft.Crm.Sandbox.SandboxCallManager Microsoft.Crm.Sandbox.SandboxCallManager::get_Instance()
0x8f5e  ldarg.0
0x8f5f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8f64  ldarg.0
0x8f65  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x8f6a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData Microsoft.Crm.Sandbox.SandboxCodeUnit::_assemblyData
0x8f6f  ldarg.0
0x8f70  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x8f75  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCodeUnit::_pluginAssemblyId
0x8f7a  callvirt instance class Microsoft.Crm.Sandbox.SandboxCallTracker Microsoft.Crm.Sandbox.SandboxCallManager::NewCallTracker(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData assemblyData, valuetype [mscorlib]System.Guid pluginAssemblyId)
0x8f7f  stloc.s  0xC
0x8f81  ldloc.s  6
0x8f83  ldloc.s  0xC
0x8f85  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x8f8a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x8f8f  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::SetExecutionId(valuetype [mscorlib]System.Guid)
0x8f94  ldnull
0x8f95  stloc.s  0xE
0x8f97  ldc.i4.1
0x8f98  stloc.s  0x11
0x8f9a  ldarg.0
0x8f9b  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x8fa0  ldfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x8fa5  ldstr    aSandboxClientN// "Sandbox Client not provided"
0x8faa  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8faf  ldarg.0
0x8fb0  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x8fb5  ldarg.0
0x8fb6  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x8fbb  ldfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x8fc0  ldarg.0
0x8fc1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8fc6  ldloc.s  6
0x8fc8  ldloc.s  0xC
0x8fca  ldloc.3
0x8fcb  ldloc.s  9
0x8fcd  ldloca.s 0x11
0x8fcf  ldloca.s 0xA
0x8fd1  call     instance void Microsoft.Crm.Sandbox.SandboxCodeUnit::ExecuteInternal(class Microsoft.Crm.Sandbox.SandboxClient client, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext sandboxTraceContext, class Microsoft.Crm.Sandbox.SandboxCallTracker callTracker, valuetype [mscorlib]System.Guid parentExecutionId, string assemblyContents, bool& isSafeToRetry, bool& executeDone)
0x8fd6  leave    loc_90DA
0x8fdb  stloc.s  0x12
0x8fdd  ldloc.s  0x12
0x8fdf  stloc.s  0xE
0x8fe1  ldarg.0
0x8fe2  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x8fe7  ldloc.s  0x12
0x8fe9  ldarg.0
0x8fea  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass24_0::context
0x8fef  ldarg.0
0x8ff0  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x8ff5  ldfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x8ffa  ldloc.s  0xC
0x8ffc  ldloc.s  0x11
0x8ffe  ldloc.s  0xF
0x9000  ldloc.s  0xB
0x9002  ldloc.3
0x9003  ldloca.s 0xD
0x9005  ldloca.s 9
0x9007  call     instance bool Microsoft.Crm.Sandbox.SandboxCodeUnit::ProcessException(class [mscorlib]System.Exception originalException, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class Microsoft.Crm.Sandbox.SandboxClient client, class Microsoft.Crm.Sandbox.SandboxCallTracker callTracker, bool isSafeToRetry, valuetype [mscorlib]System.DateTime performanceExecutionStartTime, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, valuetype [mscorlib]System.Guid parentExecutionId, [out] class [Microsoft.Crm.Core]Microsoft.Crm.CrmException& crmException, string& assemblyContents)
0x900c  brfalse.s loc_9010
0x900e  rethrow
0x9010  leave.s  loc_9074
0x9012  ldloc.s  0xC
0x9014  brfalse.s loc_901D
0x9016  ldloc.s  0xC
0x9018  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x901d  ldarg.0
0x901e  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x9023  ldfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x9028  brfalse.s loc_9073
0x902a  ldarg.0
0x902b  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x9030  ldfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x9035  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxClient::get_HostStatus()
0x903a  ldc.i4.3
0x903b  ceq
0x903d  ldc.i4.0
0x903e  ceq
0x9040  ldloc.s  0xA
0x9042  or
0x9043  brfalse.s loc_9073
0x9045  ldarg.0
0x9046  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x904b  ldfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x9050  callvirt instance bool Microsoft.Crm.Sandbox.SandboxClient::get_StopRequired()
0x9055  brfalse.s loc_9067
0x9057  ldarg.0
0x9058  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x905d  ldfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x9062  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxHost>::Stop()
0x9067  ldarg.0
0x9068  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x906d  ldnull
0x906e  stfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x9073  endfinally
0x9074  ldloc.s  0xD
0x9076  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x907b  ldc.i4   0x80044191
0x9080  bne.un.s loc_9090
0x9082  ldloc.s  9
0x9084  ldstr    aAssemblyconten// "assemblyContents"
0x9089  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x908e  br.s     loc_90CC
0x9090  ldarg.0
0x9091  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x9096  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::_attemptNumber
0x909b  ldarg.0
0x909c  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x90a1  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::_maxAttempts
0x90a6  ldc.i4.1
0x90a7  sub
0x90a8  clt
0x90aa  ldstr    aIRetrycount// "i >= retryCount"
0x90af  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x90b4  ldarg.0
0x90b5  ldfld    class Microsoft.Crm.Sandbox.SandboxCodeUnit <>c__DisplayClass24_0::<>4__this
0x90ba  ldfld    class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxCodeUnit::_sandboxClient
0x90bf  ldnull
0x90c0  ceq
0x90c2  ldstr    aSandboxClientI// "sandbox client is not null. Expecting i"...
0x90c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x90cc  ldloc.s  0x10
0x90ce  ldc.i4.1
0x90cf  add
0x90d0  stloc.s  0x10
0x90d2  ldloc.s  0x10
0x90d4  ldc.i4.2
0x90d5  blt      loc_8F3F
0x90da  ldloc.s  0xE
0x90dc  brfalse.s loc_90F7
0x90de  ldloc.s  0xE
0x90e0  ldstr    aIfThereIsNoExc// "If there is no exception we should not "...
0x90e5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x90ea  ldloc.s  0xE
0x90ec  ldstr    aRetriableFailu// "Retriable failure while executing plugi"...
0x90f1  newobj   instance void [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginRetriableException::.ctor(class [mscorlib]System.Exception, string)
0x90f6  throw
0x90f7  ldloc.s  4
0x90f9  ldc.i4.s 0x21
0x90fb  ldstr    aSandboxpluginE_10// "SandboxPlugin.Execute: exit"
0x9100  ldc.i4.0
0x9101  newarr   [mscorlib]System.Object
0x9106  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x910b  leave.s  loc_9119
0x910d  ldloc.s  6
0x910f  brfalse.s loc_9118
0x9111  ldloc.s  6
0x9113  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9118  endfinally
0x9119  ret
```
