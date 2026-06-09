# Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::Execute

- ea: `0x24db0`
- end: `0x251fd`
- name: `Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::Execute`
- size: `1101`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1c8c0`

## callees

- `0x20b40`
- `0x20b50`
- `0x20c80`
- `0x20dd0`
- `0x20ed0`
- `0x20fa0`
- `0x21a30`
- `0x21a50`
- `0x22f00`
- `0x22f70`
- `0x24d80`
- `0x24d90`
- `0x24db0`
- `0x25200`
- `0x25370`
- `0x255d0`

## string_xrefs

- `0x24e50`: `Microsoft.Crm.Extensibility.InternalOperationPlugin`
- `0x24ebc`: `PluginTrace`
- `0x25022`: `PluginTrace`
- `0x25043`: `PluginTrace`
- `0x25054`: `PluginTrace`
- `0x2513d`: `PluginTrace`
- `0x2515e`: `PluginTrace`
- `0x2516f`: `PluginTrace`
- `0x24f82`: `Web Service Plug-in failed in SdkMessageProcessingStepId: {0}; EntityName: {1}; Stage: {2}; MessageName: {3}; AssemblyName: {4}; ClassName: {5}; Exception: {6}.`
- `0x250a6`: `Web Service Plug-in failed in SdkMessageProcessingStepId: {0}; EntityName: {1}; Stage: {2}; MessageName: {3}; AssemblyName: {4}; ClassName: {5}; Exception: {6}.`

## pseudocode

```c

```

## disassembly

```asm
0x24db0  ldarg.0
0x24db1  ldarg.1
0x24db2  callvirt instance void Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::ExecuteInternal(class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x24db7  ldarg.1
0x24db8  callvirt instance void Microsoft.Crm.Extensibility.PipelineExecutionContext::SignalSuccessfulExecution()
0x24dbd  leave    loc_251FC
0x24dc2  stloc.0
0x24dc3  ldarg.1
0x24dc4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x24dc9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x24dce  brfalse.s loc_24DE4
0x24dd0  ldarg.1
0x24dd1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x24dd6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x24ddb  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::IsConnectionOpen()
0x24de0  brtrue.s loc_24DE4
0x24de2  rethrow
0x24de4  ldarg.1
0x24de5  ldloc.0
0x24de6  callvirt instance void Microsoft.Crm.Extensibility.PipelineExecutionContext::SignalFailedExecution(class [mscorlib]System.Exception e)
0x24deb  ldloc.0
0x24dec  isinst   [mscorlib]System.Threading.ThreadAbortException
0x24df1  brfalse.s loc_24DF5
0x24df3  rethrow
0x24df5  ldarg.0
0x24df6  ldarg.1
0x24df7  call     instance class Microsoft.Crm.Extensibility.StepDescription Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::GetStepDescription(class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x24dfc  stloc.1
0x24dfd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache::get_Instance()
0x24e02  ldarg.0
0x24e03  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::get_PluginTypeId()
0x24e08  ldarg.1
0x24e09  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x24e0e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache::LookupAssemblyEntry(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24e13  stloc.2
0x24e14  ldloc.2
0x24e15  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData::get_PluginAssemblySimpleName()
0x24e1a  stloc.3
0x24e1b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache::get_Instance()
0x24e20  ldarg.0
0x24e21  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::get_PluginTypeId()
0x24e26  ldarg.1
0x24e27  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x24e2c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData>::LookupEntry(void, var<u1>)
0x24e31  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_PluginTypeSimpleName()
0x24e36  stloc.s  4
0x24e38  ldloc.0
0x24e39  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x24e3e  stloc.s  5
0x24e40  ldc.i4.1
0x24e41  stloc.s  6
0x24e43  ldloc.s  4
0x24e45  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24e4a  brtrue.s loc_24E79
0x24e4c  ldloc.s  6
0x24e4e  ldloc.s  4
0x24e50  ldstr    aMicrosoftCrmEx// "Microsoft.Crm.Extensibility.InternalOpe"...
0x24e55  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x24e5a  brtrue.s loc_24E75
0x24e5c  ldarg.1
0x24e5d  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_MessageName()
0x24e62  ldstr    aExecuteworkflo// "ExecuteWorkflow"
0x24e67  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24e6c  brtrue.s loc_24E75
0x24e6e  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInScaleGroupProvisioningServiceContext()
0x24e73  br.s     loc_24E76
0x24e75  ldc.i4.1
0x24e76  and
0x24e77  stloc.s  6
0x24e79  call     class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::get_Instance()
0x24e7e  ldloc.0
0x24e7f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::IsSandboxException(class [mscorlib]System.Exception)
0x24e84  brfalse  loc_24F45
0x24e89  call     class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::get_Instance()
0x24e8e  dup
0x24e8f  ldc.i4.1
0x24e90  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::set_SkipCallStack(bool)
0x24e95  dup
0x24e96  ldc.i4.1
0x24e97  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::set_SkipExceptionMessage(bool)
0x24e9c  dup
0x24e9d  ldc.i4.1
0x24e9e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::set_SkipTraceText(bool)
0x24ea3  ldloc.0
0x24ea4  ldloca.s 0xA
0x24ea6  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToCrmException(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.CrmException&)
0x24eab  dup
0x24eac  brtrue.s loc_24EB1
0x24eae  ldloc.0
0x24eaf  br.s     loc_24EB3
0x24eb1  ldloc.s  0xA
0x24eb3  stloc.s  0xB
0x24eb5  ldloc.s  0xB
0x24eb7  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x24ebc  ldstr    aPlugintrace// "PluginTrace"
0x24ec1  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x24ec6  isinst   [mscorlib]System.String
0x24ecb  stloc.s  0xC
0x24ecd  ldloc.s  6
0x24ecf  brfalse.s loc_24F32
0x24ed1  ldloc.s  0xB
0x24ed3  ldloc.s  0xC
0x24ed5  dup
0x24ed6  brtrue.s loc_24EDE
0x24ed8  pop
0x24ed9  ldsfld   string [mscorlib]System.String::Empty
0x24ede  ldarg.1
0x24edf  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PluginTrace()
0x24ee4  dup
0x24ee5  brtrue.s loc_24EED
0x24ee7  pop
0x24ee8  ldsfld   string [mscorlib]System.String::Empty
0x24eed  ldloc.3
0x24eee  dup
0x24eef  brtrue.s loc_24EF7
0x24ef1  pop
0x24ef2  ldsfld   string [mscorlib]System.String::Empty
0x24ef7  ldloc.s  4
0x24ef9  dup
0x24efa  brtrue.s loc_24F02
0x24efc  pop
0x24efd  ldsfld   string [mscorlib]System.String::Empty
0x24f02  ldarg.0
0x24f03  ldfld    class Microsoft.Crm.Extensibility.StepDescription Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::_step
0x24f08  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.StepDescription::get_Id()
0x24f0d  stloc.s  0xD
0x24f0f  ldloca.s 0xD
0x24f11  constrained. [mscorlib]System.Guid
0x24f17  callvirt instance string [mscorlib]System.Object::ToString()
0x24f1c  ldloc.1
0x24f1d  callvirt instance string Microsoft.Crm.Extensibility.StepDescription::get_Name()
0x24f22  dup
0x24f23  brtrue.s loc_24F2B
0x24f25  pop
0x24f26  ldsfld   string [mscorlib]System.String::Empty
0x24f2b  ldloc.s  6
0x24f2d  call     void [Microsoft.Crm]Microsoft.Crm.PluginExceptionConvertor::AddPluginTrace(class [mscorlib]System.Exception, string, string, string, string, string, string, bool)
0x24f32  brtrue.s loc_24F36
0x24f34  rethrow
0x24f36  call     class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::get_Instance()
0x24f3b  ldloc.s  0xA
0x24f3d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::MarkAsSandboxException(class [mscorlib]System.Exception)
0x24f42  ldloc.s  0xA
0x24f44  throw
0x24f45  ldloc.0
0x24f46  ldarg.1
0x24f47  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PluginTrace()
0x24f4c  ldloc.3
0x24f4d  ldloc.s  4
0x24f4f  ldarg.0
0x24f50  ldfld    class Microsoft.Crm.Extensibility.StepDescription Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::_step
0x24f55  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.StepDescription::get_Id()
0x24f5a  stloc.s  0xD
0x24f5c  ldloca.s 0xD
0x24f5e  constrained. [mscorlib]System.Guid
0x24f64  callvirt instance string [mscorlib]System.Object::ToString()
0x24f69  ldloc.1
0x24f6a  callvirt instance string Microsoft.Crm.Extensibility.StepDescription::get_Name()
0x24f6f  ldc.i4.0
0x24f70  ldloc.s  6
0x24f72  call     class [mscorlib]System.Exception [Microsoft.Crm]Microsoft.Crm.PluginExceptionConvertor::ConvertPluginException(class [mscorlib]System.Exception, string, string, string, string, string, bool, bool)
0x24f77  stloc.s  7
0x24f79  ldloc.0
0x24f7a  ldarg.1
0x24f7b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x24f80  ldc.i4.s 0x1A
0x24f82  ldstr    aWebServicePlug// "Web Service Plug-in failed in SdkMessag"...
0x24f87  ldc.i4.7
0x24f88  newarr   [mscorlib]System.Object
0x24f8d  dup
0x24f8e  ldc.i4.0
0x24f8f  ldarg.0
0x24f90  ldfld    class Microsoft.Crm.Extensibility.StepDescription Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::_step
0x24f95  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.StepDescription::get_Id()
0x24f9a  box      [mscorlib]System.Guid
0x24f9f  stelem.ref
0x24fa0  dup
0x24fa1  ldc.i4.1
0x24fa2  ldarg.1
0x24fa3  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PrimaryEntityName()
0x24fa8  stelem.ref
0x24fa9  dup
0x24faa  ldc.i4.2
0x24fab  ldarg.1
0x24fac  callvirt instance int32 Microsoft.Crm.Extensibility.PipelineExecutionContext::get_Stage()
0x24fb1  box      [mscorlib]System.Int32
0x24fb6  stelem.ref
0x24fb7  dup
0x24fb8  ldc.i4.3
0x24fb9  ldarg.1
0x24fba  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_MessageName()
0x24fbf  stelem.ref
0x24fc0  dup
0x24fc1  ldc.i4.4
0x24fc2  ldarg.0
0x24fc3  callvirt instance class [mscorlib]System.Type Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::get_PluginType()
0x24fc8  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x24fcd  stelem.ref
0x24fce  dup
0x24fcf  ldc.i4.5
0x24fd0  ldarg.0
0x24fd1  callvirt instance class [mscorlib]System.Type Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::get_PluginType()
0x24fd6  callvirt instance string [mscorlib]System.Type::get_FullName()
0x24fdb  stelem.ref
0x24fdc  dup
0x24fdd  ldc.i4.6
0x24fde  ldloc.s  5
0x24fe0  stelem.ref
0x24fe1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24fe6  ldloc.s  7
0x24fe8  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmExceptionHandler::RetrieveCrmException(class [mscorlib]System.Exception)
0x24fed  stloc.s  8
0x24fef  ldloc.s  8
0x24ff1  brfalse.s loc_24FFE
0x24ff3  ldarg.0
0x24ff4  ldloc.s  8
0x24ff6  ldarg.1
0x24ff7  call     instance class [mscorlib]System.Exception Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::WrapExceptionToThrow(class [Microsoft.Crm.Core]Microsoft.Crm.CrmException exception, class Microsoft.Crm.Extensibility.PipelineExecutionContext context)
0x24ffc  stloc.s  7
0x24ffe  ldloc.s  7
0x25000  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.PluginExecutionExceptionHandler::RetrieveInvalidPluginExecutionException(class [mscorlib]System.Exception)
0x25005  stloc.s  9
0x25007  ldloc.s  9
0x25009  brfalse.s loc_25060
0x2500b  ldloc.s  9
0x2500d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x25012  ldloc.s  9
0x25014  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException::.ctor(string, class [mscorlib]System.Exception)
0x25019  stloc.s  7
0x2501b  ldloc.s  9
0x2501d  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x25022  ldstr    aPlugintrace// "PluginTrace"
0x25027  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x2502c  isinst   [mscorlib]System.String
0x25031  stloc.s  0xE
0x25033  ldloc.s  0xE
0x25035  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2503a  brtrue.s loc_25060
0x2503c  ldloc.s  9
0x2503e  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x25043  ldstr    aPlugintrace// "PluginTrace"
0x25048  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x2504d  ldloc.s  7
0x2504f  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x25054  ldstr    aPlugintrace// "PluginTrace"
0x25059  ldloc.s  0xE
0x2505b  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x25060  ldloc.s  7
0x25062  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x25067  brtrue   loc_251F9
0x2506c  ldloc.s  7
0x2506e  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException
0x25073  brtrue   loc_251F9
0x25078  ldloc.s  7
0x2507a  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x2507f  brtrue   loc_251F9
0x25084  ldloc.s  7
0x25086  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.SdkExceptionBase
0x2508b  brtrue   loc_251F9
0x25090  ldloc.s  7
0x25092  isinst   [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.Exceptions.AuthorizationException
0x25097  brtrue   loc_251F9
0x2509c  ldloc.2
0x2509d  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.GenericSharedOrganizationData`1<class [mscorlib]System.Reflection.Assembly>::get_IsSystem()
0x250a2  brfalse.s loc_25121
0x250a4  ldloc.s  7
0x250a6  ldstr    aWebServicePlug// "Web Service Plug-in failed in SdkMessag"...
0x250ab  ldc.i4.7
0x250ac  newarr   [mscorlib]System.Object
0x250b1  dup
0x250b2  ldc.i4.0
0x250b3  ldarg.0
0x250b4  ldfld    class Microsoft.Crm.Extensibility.StepDescription Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::_step
0x250b9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.StepDescription::get_Id()
0x250be  box      [mscorlib]System.Guid
0x250c3  stelem.ref
0x250c4  dup
0x250c5  ldc.i4.1
0x250c6  ldarg.1
0x250c7  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PrimaryEntityName()
0x250cc  stelem.ref
0x250cd  dup
0x250ce  ldc.i4.2
0x250cf  ldarg.1
0x250d0  callvirt instance int32 Microsoft.Crm.Extensibility.PipelineExecutionContext::get_Stage()
0x250d5  box      [mscorlib]System.Int32
0x250da  stelem.ref
0x250db  dup
0x250dc  ldc.i4.3
0x250dd  ldarg.1
0x250de  callvirt instance string Microsoft.Crm.Extensibility.PipelineExecutionContext::get_MessageName()
0x250e3  stelem.ref
0x250e4  dup
0x250e5  ldc.i4.4
0x250e6  ldarg.0
0x250e7  callvirt instance class [mscorlib]System.Type Microsoft.Crm.Extensibility.VersionedPluginProxyStepBase::get_PluginType()
0x250ec  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x250f1  stelem.ref
0x250f2  dup
0x250f3  ldc.i4.5
  ... truncated ...
```
