# Microsoft.Crm.Sandbox.SandboxWorker::InitializeSandboxServices

- ea: `0x3300`
- end: `0x3442`
- name: `Microsoft.Crm.Sandbox.SandboxWorker::InitializeSandboxServices`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x3090`
- `0x3630`

## callees

- `0x90`
- `0x3e0`
- `0x810`
- `0x990`
- `0xb50`
- `0xd40`
- `0x3300`
- `0x3450`
- `0x4930`

## string_xrefs

- `0x3344`: `PluginSecureStore`

## pseudocode

```c

```

## disassembly

```asm
0x3300  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::.ctor()
0x3305  stloc.0
0x3306  ldloc.0
0x3307  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext
0x330c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3311  ldarg.1
0x3312  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x3317  ldarg.2
0x3318  brfalse.s loc_332B
0x331a  ldloc.0
0x331b  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IServiceEndpointNotificationService
0x3320  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3325  ldarg.2
0x3326  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x332b  ldloc.0
0x332c  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0x3331  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3336  ldarg.3
0x3337  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x333c  ldarg.1
0x333d  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext)
0x3342  stloc.1
0x3343  ldarg.0
0x3344  ldstr    aPluginsecurest// "PluginSecureStore"
0x3349  call     instance bool Microsoft.Crm.Sandbox.SandboxWorker::IsFeatureEnabled(string featureName)
0x334e  brfalse  loc_340B
0x3353  ldloc.1
0x3354  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3359  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::set_UserId(valuetype [mscorlib]System.Guid)
0x335e  ldarg.s  4
0x3360  callvirt instance class [mscorlib]System.Reflection.AssemblyName [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_AssemblyName()
0x3365  ldarg.s  4
0x3367  callvirt instance bool [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_IsStrongNameSigned()
0x336c  call     string [Microsoft.Crm.ServiceBus]Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.AssemblyName, bool)
0x3371  ldarg.s  5
0x3373  ldarg.1
0x3374  ldloc.1
0x3375  ldarg.s  6
0x3377  newobj   instance void Microsoft.Crm.Sandbox.AssemblyAuthenticationContextProvider::.ctor(string assemblyName, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext sdkContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter)
0x337c  stloc.3
0x337d  ldarg.s  4
0x337f  callvirt instance class [mscorlib]System.Reflection.AssemblyName [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_AssemblyName()
0x3384  ldarg.s  4
0x3386  callvirt instance bool [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_IsStrongNameSigned()
0x338b  call     string [Microsoft.Crm.ServiceBus]Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.AssemblyName, bool)
0x3390  ldarg.s  5
0x3392  ldarg.1
0x3393  ldloc.1
0x3394  ldarg.s  6
0x3396  newobj   instance void Microsoft.Crm.Sandbox.LocalConfigStoreProvider::.ctor(string assemblyName, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext sdkContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter)
0x339b  ldloc.3
0x339c  newobj   instance void Microsoft.Crm.Sandbox.AssemblyAuthenticationContextWrapper::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IAssemblyAuthenticationContext fulltrustedAuthenticationContext)
0x33a1  stloc.s  4
0x33a3  newobj   instance void Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore localConfigStore)
0x33a8  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore)
0x33ad  stloc.s  5
0x33af  ldarg.s  4
0x33b1  callvirt instance class [mscorlib]System.Reflection.AssemblyName [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_AssemblyName()
0x33b6  ldarg.s  4
0x33b8  callvirt instance bool [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_IsStrongNameSigned()
0x33bd  call     string [Microsoft.Crm.ServiceBus]Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.AssemblyName, bool)
0x33c2  ldloc.3
0x33c3  ldarg.s  5
0x33c5  ldarg.1
0x33c6  ldloc.1
0x33c7  ldarg.s  6
0x33c9  newobj   instance void Microsoft.Crm.Sandbox.KeyVaultClientProvider::.ctor(string assemblyName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IAssemblyAuthenticationContext authenticationContex, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext sdkContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter)
0x33ce  newobj   instance void Microsoft.Crm.Sandbox.KeyVaultClientWrapper::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IKeyVaultClient trustedKeyVaultClient)
0x33d3  stloc.s  6
0x33d5  ldloc.0
0x33d6  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IAssemblyAuthenticationContext
0x33db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33e0  ldloc.s  4
0x33e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x33e7  ldloc.0
0x33e8  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ILocalConfigStore
0x33ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33f2  ldloc.s  5
0x33f4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x33f9  ldloc.0
0x33fa  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IKeyVaultClient
0x33ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3404  ldloc.s  6
0x3406  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x340b  ldarg.s  4
0x340d  callvirt instance class [mscorlib]System.Reflection.AssemblyName [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_AssemblyName()
0x3412  ldarg.s  4
0x3414  callvirt instance bool [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_IsStrongNameSigned()
0x3419  call     string [Microsoft.Crm.ServiceBus]Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.AssemblyName, bool)
0x341e  ldarg.s  5
0x3420  ldarg.1
0x3421  ldloc.1
0x3422  ldarg.s  6
0x3424  newobj   instance void Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::.ctor(string assemblyName, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext sdkContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter)
0x3429  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxEntityDataSourceRetrieverService::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalDataSourceRetrieverService)
0x342e  stloc.2
0x342f  ldloc.0
0x3430  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IEntityDataSourceRetrieverService
0x3435  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x343a  ldloc.2
0x343b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x3440  ldloc.0
0x3441  ret
```
