# Microsoft.Crm.Asynchronous.EventOperation::CreateAsyncResultFromException

- ea: `0x2fc0`
- end: `0x314f`
- name: `Microsoft.Crm.Asynchronous.EventOperation::CreateAsyncResultFromException`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2f90`

## callees

- `0x2b10`
- `0x2c30`
- `0x2d80`
- `0x2fc0`

## string_xrefs

- `0x3001`: `Could not find the plugin assembly or type to execute.`
- `0x30a7`: `PluginTrace`
- `0x30c4`: `PluginTrace`
- `0x30cf`: `PluginTrace`

## pseudocode

```c

```

## disassembly

```asm
0x2fc0  call     class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandler [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandlerFactory::CreateDefault()
0x2fc5  stloc.0
0x2fc6  ldarg.1
0x2fc7  callvirt instance class [mscorlib]System.IServiceProvider [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_ServiceProvider()
0x2fcc  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService
0x2fd1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fd6  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x2fdb  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncTracingService
0x2fe0  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncTracingService::get_TraceInfo()
0x2fe5  stloc.1
0x2fe6  ldarg.0
0x2fe7  ldarg.1
0x2fe8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData Microsoft.Crm.Asynchronous.EventOperation::GetPluginAssembly(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x2fed  stloc.2
0x2fee  ldarg.0
0x2fef  ldarg.1
0x2ff0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData Microsoft.Crm.Asynchronous.EventOperation::GetPluginType(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x2ff5  stloc.3
0x2ff6  ldloc.2
0x2ff7  brfalse.s loc_2FFC
0x2ff9  ldloc.3
0x2ffa  brtrue.s loc_3012
0x2ffc  ldc.i4   0x80040216
0x3001  ldstr    aCouldNotFindTh// "Could not find the plugin assembly or t"...
0x3006  ldc.i4.0
0x3007  newarr   [mscorlib]System.Object
0x300c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0x3011  ret
0x3012  ldloc.2
0x3013  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData::get_PluginAssemblySimpleName()
0x3018  stloc.s  4
0x301a  ldloc.3
0x301b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_PluginTypeSimpleName()
0x3020  stloc.s  5
0x3022  ldarg.1
0x3023  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription Microsoft.Crm.Asynchronous.EventOperation::GetProcessingStep(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext context)
0x3028  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription::get_Name()
0x302d  stloc.s  6
0x302f  ldarg.2
0x3030  ldloc.1
0x3031  ldloc.s  4
0x3033  ldloc.s  5
0x3035  ldarg.1
0x3036  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OwningExtension()
0x303b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x3040  stloc.s  9
0x3042  ldloca.s 9
0x3044  constrained. [mscorlib]System.Guid
0x304a  callvirt instance string [mscorlib]System.Object::ToString()
0x304f  ldloc.s  6
0x3051  ldc.i4.1
0x3052  ldc.i4.1
0x3053  call     class [mscorlib]System.Exception [Microsoft.Crm]Microsoft.Crm.PluginExceptionConvertor::ConvertPluginException(class [mscorlib]System.Exception, string, string, string, string, string, bool, bool)
0x3058  starg.s  2
0x305a  ldloc.0
0x305b  ldarg.2
0x305c  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandler::Handle(class [mscorlib]System.Exception)
0x3061  stloc.s  7
0x3063  ldnull
0x3064  stloc.s  8
0x3066  ldloc.s  7
0x3068  callvirt instance valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorActionType [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction::get_Type()
0x306d  stloc.s  0xA
0x306f  ldloc.s  0xA
0x3071  switch   loc_3093, loc_30EB, loc_30E1, loc_30FA, loc_3144, loc_313A
0x308e  br       loc_314C
0x3093  ldarg.2
0x3094  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3099  ldarg.2
0x309a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException::.ctor(string, class [mscorlib]System.Exception)
0x309f  stloc.s  0xB
0x30a1  ldarg.2
0x30a2  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x30a7  ldstr    aPlugintrace// "PluginTrace"
0x30ac  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x30b1  isinst   [mscorlib]System.String
0x30b6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x30bb  brtrue.s loc_30DE
0x30bd  ldloc.s  0xB
0x30bf  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x30c4  ldstr    aPlugintrace// "PluginTrace"
0x30c9  ldarg.2
0x30ca  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x30cf  ldstr    aPlugintrace// "PluginTrace"
0x30d4  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x30d9  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x30de  ldloc.s  0xB
0x30e0  throw
0x30e1  ldarg.2
0x30e2  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x30e7  stloc.s  8
0x30e9  br.s     loc_314C
0x30eb  ldarg.2
0x30ec  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x30f1  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRetryResult::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult)
0x30f6  stloc.s  8
0x30f8  br.s     loc_314C
0x30fa  ldloc.s  7
0x30fc  callvirt instance int32 [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction::get_ErrorCode()
0x3101  ldc.i4   0x80044179
0x3106  bne.un.s loc_3130
0x3108  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x310d  stloc.s  0xC
0x310f  ldloca.s 0xC
0x3111  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x3116  ldstr    aPostponeappfab// "PostponeAppFabricRequestsInMinutes"
0x311b  ldc.i4.0
0x311c  callvirt T0x2B000002
0x3121  conv.r8
0x3122  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x3127  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor(valuetype [mscorlib]System.DateTime)
0x312c  stloc.s  8
0x312e  br.s     loc_314C
0x3130  ldarg.2
0x3131  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSystemPausedResult::.ctor(class [mscorlib]System.Exception)
0x3136  stloc.s  8
0x3138  br.s     loc_314C
0x313a  ldarg.2
0x313b  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor(class [mscorlib]System.Exception)
0x3140  stloc.s  8
0x3142  br.s     loc_314C
0x3144  ldarg.2
0x3145  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor(class [mscorlib]System.Exception)
0x314a  stloc.s  8
0x314c  ldloc.s  8
0x314e  ret
```
