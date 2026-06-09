# Microsoft.Crm.Sandbox.SandboxPluginHelper::GetOrganizationService

- ea: `0x3630`
- end: `0x37b7`
- name: `Microsoft.Crm.Sandbox.SandboxPluginHelper::GetOrganizationService`
- size: `391`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x35c0`
- `0x5590`

## callees

- `0x3630`
- `0x3880`

## string_xrefs

- `0x365b`: `SandboxPluginHelper.GetOrganizationService: sync`
- `0x36c4`: `SandboxPluginHelper.GetOrganizationService: async`

## pseudocode

```c

```

## disassembly

```asm
0x3630  ldarg.0
0x3631  ldstr    aContext// "context"
0x3636  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x363b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3640  stloc.2
0x3641  ldarg.0
0x3642  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x3647  stloc.3
0x3648  ldarg.0
0x3649  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorkflowContext
0x364e  stloc.s  4
0x3650  ldloc.3
0x3651  brfalse.s loc_369E
0x3653  ldarg.0
0x3654  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x3659  ldc.i4.s 0x21
0x365b  ldstr    aSandboxpluginh_0// "SandboxPluginHelper.GetOrganizationServ"...
0x3660  ldc.i4.0
0x3661  newarr   [mscorlib]System.Object
0x3666  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x366b  ldarg.2
0x366c  brfalse.s loc_3682
0x366e  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin::get_Application()
0x3673  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ApplicationOrigin
0x3678  dup
0x3679  ldc.i4.1
0x367a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ApplicationOrigin::set_Feature(int32)
0x367f  stloc.0
0x3680  br.s     loc_3689
0x3682  ldloc.3
0x3683  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_CallerOrigin()
0x3688  stloc.0
0x3689  ldloc.3
0x368a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_CorrelationUpdatedTime()
0x368f  stloc.1
0x3690  ldloc.3
0x3691  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_CorrelationToken()
0x3696  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_TransactionContextId()
0x369b  stloc.2
0x369c  br.s     loc_36DE
0x369e  ldloc.s  4
0x36a0  brfalse.s loc_36BC
0x36a2  ldloc.s  4
0x36a4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorkflowContext::get_CallerOrigin()
0x36a9  stloc.0
0x36aa  ldloc.s  4
0x36ac  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorkflowContext::get_CorrelationUpdateTime()
0x36b1  stloc.1
0x36b2  ldloc.s  4
0x36b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorkflowContext::get_TransactionContextId()
0x36b9  stloc.2
0x36ba  br.s     loc_36DE
0x36bc  ldarg.0
0x36bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x36c2  ldc.i4.s 0x21
0x36c4  ldstr    aSandboxpluginh_1// "SandboxPluginHelper.GetOrganizationServ"...
0x36c9  ldc.i4.0
0x36ca  newarr   [mscorlib]System.Object
0x36cf  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x36d4  ldarg.0
0x36d5  ldloca.s 0
0x36d7  ldloca.s 1
0x36d9  call     void Microsoft.Crm.Sandbox.SandboxPluginHelper::GetAsyncInfo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, [out] class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin& callerOrigin, [out] valuetype [mscorlib]System.DateTime& correlationUpdatedTime)
0x36de  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0x36e3  stloc.s  5
0x36e5  ldloc.s  5
0x36e7  ldarg.0
0x36e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x36ed  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x36f2  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x36f7  brtrue.s loc_3701
0x36f9  ldarg.0
0x36fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x36ff  br.s     loc_3706
0x3701  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3706  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_CorrelationId(valuetype [mscorlib]System.Guid)
0x370b  ldloc.s  5
0x370d  ldarg.0
0x370e  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x3713  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_Depth(int32)
0x3718  ldloc.s  5
0x371a  ldloc.1
0x371b  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_CorrelationUpdatedTime(valuetype [mscorlib]System.DateTime)
0x3720  ldloc.s  5
0x3722  ldloc.2
0x3723  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_TransactionContextId(valuetype [mscorlib]System.Guid)
0x3728  ldloc.s  5
0x372a  ldarg.0
0x372b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x3730  stloc.s  7
0x3732  ldloca.s 7
0x3734  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x3739  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_RequestId(valuetype [mscorlib]System.Guid)
0x373e  ldloc.s  5
0x3740  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3745  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_ParentPluginExecutionId(valuetype [mscorlib]System.Guid)
0x374a  ldarg.0
0x374b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3750  brfalse.s loc_3792
0x3752  ldarg.0
0x3753  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3758  ldstr    aParentexecutio// "parentExecutionId"
0x375d  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x3762  brfalse.s loc_3792
0x3764  ldarg.0
0x3765  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x376a  ldstr    aParentexecutio// "parentExecutionId"
0x376f  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x3774  brfalse.s loc_3792
0x3776  ldloc.s  5
0x3778  ldarg.0
0x3779  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x377e  ldstr    aParentexecutio// "parentExecutionId"
0x3783  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x3788  unbox.any [mscorlib]System.Guid
0x378d  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_ParentPluginExecutionId(valuetype [mscorlib]System.Guid)
0x3792  ldloc.0
0x3793  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x3798  stloc.s  6
0x379a  ldc.i4.1
0x379b  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::set_LoadMethod(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LoadMethod)
0x37a0  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0x37a5  ldarg.0
0x37a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x37ab  ldarg.1
0x37ac  ldloc.s  5
0x37ae  ldloc.s  6
0x37b0  ldnull
0x37b1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [mscorlib]System.Reflection.Assembly)
0x37b6  ret
```
