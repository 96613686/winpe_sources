# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::Execute

- ea: `0x7b0`
- end: `0xe55`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::Execute`
- size: `1701`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x720`
- `0x7b0`
- `0xe60`
- `0x1010`
- `0x1060`
- `0x10d0`
- `0x1790`
- `0x18d0`
- `0x1990`
- `0x1a20`
- `0x1ba0`
- `0x1c00`
- `0x1e80`
- `0x1eb0`
- `0x1ec0`
- `0x1ef0`
- `0x1f00`
- `0x1fa0`
- `0x1fc0`
- `0x1fd0`
- `0x1ff0`
- `0x2010`
- `0x2030`
- `0x2050`

## string_xrefs

- `0x925`: `Microsoft.Xrm.Sdk.IPlugin`
- `0x937`: `SandboxAppDomainHelper.Execute: The plug-in type does not implement Microsoft.Xrm.Sdk.IPlugin: `
- `0x9d2`: `SandboxAppDomainHelper.Execute.CreateSandboxCodeUnit`
- `0xa29`: `SandboxAppDomainHelper.Execute: exception from plugin constructor: `
- `0xa5f`: `SandboxAppDomainHelper.Execute: Could not create the plug-in type from the plug-in assembly: `
- `0xa87`: `SandboxAppDomainHelper.Execute: Could not create the plug-in interface from the plug-in assembly: `
- `0xabd`: `PluginExecutionTimeout`
- `0xad0`: `PluginExecutionTimeout`
- `0xb04`: `SandboxAppDomainHelper.Execute.TimeToStartThread`
- `0xc2f`: `Couldn’t complete execution of the {0} plug-in within the {1}-minute limit.`
- `0xc8a`: `Unhandled exception in pluginCode: {0}`
- `0xca4`: `Unhandled exception in pluginCode. Unknown crash exception.`
- `0xccd`: `SandboxAppDomainHelper.Execute.IPlugin.Exeption`
- `0xcfd`: `SandboxAppDomainHelper.Execute: exception from plugin: `
- `0xd40`: `SandboxAppDomainHelper.Execute: plugin executed OK`
- `0xda1`: `ExceptionFromPluginConstructor`
- `0xdd8`: `ExceptionFromPluginConstructor`
- `0xdb2`: `ExceptionFromPluginExecute`
- `0xdee`: `ExceptionFromPluginExecute`

## pseudocode

```c

```

## disassembly

```asm
0x7b0  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x7b5  stloc.0
0x7b6  ldc.i4.0
0x7b7  stloc.1
0x7b8  ldloc.0
0x7b9  ldarg.s  6
0x7bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7c0  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0x7c5  ldstr    aSandboxappdoma_11// "SandboxAppDomainHelper.Execute"
0x7ca  ldc.i4.3
0x7cb  ldloc.0
0x7cc  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0x7d1  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x7d6  stloc.2
0x7d7  newobj   instance void <>c__DisplayClass14_1::.ctor()
0x7dc  stloc.3
0x7dd  ldloc.3
0x7de  ldloc.0
0x7df  stfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_1::CS$<>8__locals1
0x7e4  ldstr    aSandboxappdoma_12// "SandboxAppDomainHelper.Execute.Validate"...
0x7e9  ldc.i4.3
0x7ea  ldloc.3
0x7eb  ldfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_1::CS$<>8__locals1
0x7f0  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0x7f5  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x7fa  stloc.s  7
0x7fc  ldarg.0
0x7fd  ldarg.3
0x7fe  ldarg.s  6
0x800  ldarg.2
0x801  call     instance void Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ValidateArguments(string typeName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext requestContext, class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> sandboxServices)
0x806  leave.s  loc_814
0x808  ldloc.s  7
0x80a  brfalse.s loc_813
0x80c  ldloc.s  7
0x80e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x813  endfinally
0x814  ldloc.3
0x815  ldfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_1::CS$<>8__locals1
0x81a  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0x81f  ldc.i4.3
0x820  ldstr    aSandboxappdoma_13// "SandboxAppDomainHelper.Execute: enter"
0x825  ldnull
0x826  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x82b  ldstr    aSandboxappdoma_14// "SandboxAppDomainHelper.Execute.SetProxy"...
0x830  ldc.i4.3
0x831  ldloc.3
0x832  ldfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_1::CS$<>8__locals1
0x837  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0x83c  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x841  stloc.s  7
0x843  ldarg.0
0x844  ldarg.1
0x845  call     instance void Microsoft.Crm.Sandbox.SandboxAppDomainHelper::SetProxyTypesAssembly(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory)
0x84a  leave.s  loc_858
0x84c  ldloc.s  7
0x84e  brfalse.s loc_857
0x850  ldloc.s  7
0x852  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x857  endfinally
0x858  ldarg.2
0x859  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x85e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x863  ldarg.s  6
0x865  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x86a  ldloc.3
0x86b  ldarg.2
0x86c  newobj   instance void Microsoft.Crm.Sandbox.SandboxServiceProvider::.ctor(class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> services)
0x871  stfld    class Microsoft.Crm.Sandbox.SandboxServiceProvider <>c__DisplayClass14_1::serviceProvider
0x876  ldloc.3
0x877  ldfld    class Microsoft.Crm.Sandbox.SandboxServiceProvider <>c__DisplayClass14_1::serviceProvider
0x87c  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService
0x881  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x886  callvirt instance object Microsoft.Crm.Sandbox.SandboxServiceProvider::GetService(class [mscorlib]System.Type serviceType)
0x88b  castclass Microsoft.Crm.Sandbox.SandboxTracingService
0x890  stloc.s  4
0x892  ldc.i4.0
0x893  stloc.s  5
0x895  ldc.i4.0
0x896  stloc.s  6
0x898  newobj   instance void <>c__DisplayClass14_2::.ctor()
0x89d  stloc.s  8
0x89f  ldloc.s  8
0x8a1  ldloc.3
0x8a2  stfld    class <>c__DisplayClass14_1 <>c__DisplayClass14_2::CS$<>8__locals2
0x8a7  ldarg.s  8
0x8a9  call     void Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ChaosFailure(bool chaosFailAppDomain)
0x8ae  ldstr    aSandboxappdoma_15// "SandboxAppDomainHelper.Execute.GetType"
0x8b3  ldc.i4.3
0x8b4  ldloc.s  8
0x8b6  ldfld    class <>c__DisplayClass14_1 <>c__DisplayClass14_2::CS$<>8__locals2
0x8bb  ldfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_1::CS$<>8__locals1
0x8c0  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0x8c5  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x8ca  stloc.s  7
0x8cc  ldarg.0
0x8cd  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x8d2  ldarg.3
0x8d3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x8d8  stloc.s  9
0x8da  ldloc.s  9
0x8dc  ldnull
0x8dd  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8e2  brfalse.s loc_8F7
0x8e4  ldc.i4.0
0x8e5  stloc.1
0x8e6  ldstr    aSandboxappdoma_16// "SandboxAppDomainHelper.Execute: The plu"...
0x8eb  ldarg.3
0x8ec  call     string [mscorlib]System.String::Concat(string, string)
0x8f1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8f6  throw
0x8f7  leave.s  loc_905
0x8f9  ldloc.s  7
0x8fb  brfalse.s loc_904
0x8fd  ldloc.s  7
0x8ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x904  endfinally
0x905  ldstr    aSandboxappdoma_17// "SandboxAppDomainHelper.Execute.GetInter"...
0x90a  ldc.i4.3
0x90b  ldloc.s  8
0x90d  ldfld    class <>c__DisplayClass14_1 <>c__DisplayClass14_2::CS$<>8__locals2
0x912  ldfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_1::CS$<>8__locals1
0x917  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0x91c  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x921  stloc.s  7
0x923  ldloc.s  9
0x925  ldstr    aMicrosoftXrmSd_2// "Microsoft.Xrm.Sdk.IPlugin"
0x92a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetInterface(string)
0x92f  ldnull
0x930  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x935  brfalse.s loc_948
0x937  ldstr    aSandboxappdoma_18// "SandboxAppDomainHelper.Execute: The plu"...
0x93c  ldarg.3
0x93d  call     string [mscorlib]System.String::Concat(string, string)
0x942  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x947  throw
0x948  leave.s  loc_956
0x94a  ldloc.s  7
0x94c  brfalse.s loc_955
0x94e  ldloc.s  7
0x950  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x955  endfinally
0x956  ldnull
0x957  stloc.s  0xA
0x959  ldloc.s  9
0x95b  ldc.i4.2
0x95c  newarr   [mscorlib]System.Type
0x961  dup
0x962  ldc.i4.0
0x963  ldtoken  [mscorlib]System.String
0x968  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x96d  stelem.ref
0x96e  dup
0x96f  ldc.i4.1
0x970  ldtoken  [mscorlib]System.String
0x975  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x97a  stelem.ref
0x97b  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(class [mscorlib]System.Type[])
0x980  dup
0x981  stloc.s  0xB
0x983  ldnull
0x984  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Inequality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x989  brfalse.s loc_99F
0x98b  ldc.i4.2
0x98c  newarr   [mscorlib]System.Object
0x991  dup
0x992  ldc.i4.0
0x993  ldarg.s  4
0x995  stelem.ref
0x996  dup
0x997  ldc.i4.1
0x998  ldarg.s  5
0x99a  stelem.ref
0x99b  stloc.s  0xA
0x99d  br.s     loc_9D1
0x99f  ldloc.s  9
0x9a1  ldc.i4.1
0x9a2  newarr   [mscorlib]System.Type
0x9a7  dup
0x9a8  ldc.i4.0
0x9a9  ldtoken  [mscorlib]System.String
0x9ae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9b3  stelem.ref
0x9b4  callvirt instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(class [mscorlib]System.Type[])
0x9b9  dup
0x9ba  stloc.s  0xB
0x9bc  ldnull
0x9bd  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Inequality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x9c2  brfalse.s loc_9D1
0x9c4  ldc.i4.1
0x9c5  newarr   [mscorlib]System.Object
0x9ca  dup
0x9cb  ldc.i4.0
0x9cc  ldarg.s  4
0x9ce  stelem.ref
0x9cf  stloc.s  0xA
0x9d1  nop
0x9d2  ldstr    aSandboxappdoma_19// "SandboxAppDomainHelper.Execute.CreateSa"...
0x9d7  ldc.i4.3
0x9d8  ldloc.s  8
0x9da  ldfld    class <>c__DisplayClass14_1 <>c__DisplayClass14_2::CS$<>8__locals2
0x9df  ldfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_1::CS$<>8__locals1
0x9e4  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0x9e9  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x9ee  stloc.s  7
0x9f0  ldarg.0
0x9f1  ldloc.s  0xB
0x9f3  ldloc.s  0xA
0x9f5  ldarg.3
0x9f6  call     instance object Microsoft.Crm.Sandbox.SandboxAppDomainHelper::CreateSandboxCodeUnit(class [mscorlib]System.Reflection.ConstructorInfo constructorInfo, object[] args, string typeName)
0x9fb  stloc.s  0xC
0x9fd  leave.s  loc_A0B
0x9ff  ldloc.s  7
0xa01  brfalse.s loc_A0A
0xa03  ldloc.s  7
0xa05  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa0a  endfinally
0xa0b  leave.s  loc_A5B
0xa0d  stloc.s  0xD
0xa0f  ldloc.s  8
0xa11  ldfld    class <>c__DisplayClass14_1 <>c__DisplayClass14_2::CS$<>8__locals2
0xa16  ldfld    class <>c__DisplayClass14_0 <>c__DisplayClass14_1::CS$<>8__locals1
0xa1b  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass14_0::orgId
0xa20  ldc.i4.1
0xa21  ldc.i4.4
0xa22  newarr   [mscorlib]System.Object
0xa27  dup
0xa28  ldc.i4.0
0xa29  ldstr    aSandboxappdoma_20// "SandboxAppDomainHelper.Execute: excepti"...
0xa2e  stelem.ref
0xa2f  dup
0xa30  ldc.i4.1
0xa31  ldloc.s  0xD
0xa33  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xa38  stelem.ref
0xa39  dup
0xa3a  ldc.i4.2
0xa3b  ldstr    asc_38FC// ": "
0xa40  stelem.ref
0xa41  dup
0xa42  ldc.i4.3
0xa43  ldloc.s  0xD
0xa45  callvirt instance string [mscorlib]System.Object::ToString()
0xa4a  stelem.ref
0xa4b  call     string [mscorlib]System.String::Concat(object[])
0xa50  ldnull
0xa51  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0xa56  ldc.i4.1
0xa57  stloc.s  5
0xa59  rethrow
0xa5b  ldloc.s  0xC
0xa5d  brtrue.s loc_A70
0xa5f  ldstr    aSandboxappdoma_21// "SandboxAppDomainHelper.Execute: Could n"...
0xa64  ldarg.3
0xa65  call     string [mscorlib]System.String::Concat(string, string)
0xa6a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa6f  throw
0xa70  ldloc.s  8
0xa72  ldloc.s  0xC
0xa74  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin
0xa79  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin <>c__DisplayClass14_2::pluginInterface
0xa7e  ldloc.s  8
0xa80  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin <>c__DisplayClass14_2::pluginInterface
0xa85  brtrue.s loc_A98
0xa87  ldstr    aSandboxappdoma_22// "SandboxAppDomainHelper.Execute: Could n"...
0xa8c  ldarg.3
0xa8d  call     string [mscorlib]System.String::Concat(string, string)
0xa92  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa97  throw
0xa98  nop
0xa99  newobj   instance void <>c__DisplayClass14_3::.ctor()
0xa9e  stloc.s  0xE
0xaa0  ldloc.s  0xE
0xaa2  ldloc.s  8
0xaa4  stfld    class <>c__DisplayClass14_2 <>c__DisplayClass14_3::CS$<>8__locals3
0xaa9  ldc.i4.s 0x78
0xaab  stloc.s  0xF
0xaad  ldarg.s  6
0xaaf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0xab4  brfalse.s loc_AE1
0xab6  ldarg.s  6
0xab8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0xabd  ldstr    aPluginexecutio// "PluginExecutionTimeout"
0xac2  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xac7  brfalse.s loc_AE1
0xac9  ldarg.s  6
0xacb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0xad0  ldstr    aPluginexecutio// "PluginExecutionTimeout"
0xad5  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xada  unbox.any [mscorlib]System.Int32
0xadf  stloc.s  0xF
0xae1  ldloc.s  0xE
0xae3  ldc.i4.0
0xae4  newobj   instance void [mscorlib]System.Threading.AutoResetEvent::.ctor(bool)
0xae9  stfld    class [mscorlib]System.Threading.AutoResetEvent <>c__DisplayClass14_3::ExecuteComplete
0xaee  ldloc.s  0xE
0xaf0  ldnull
0xaf1  stfld    class [mscorlib]System.Exception <>c__DisplayClass14_3::executeException
0xaf6  ldloc.s  0xE
0xaf8  ldsfld   object Microsoft.Crm.Sandbox.SandboxTraceContextHelper::TraceParameters
  ... truncated ...
```
