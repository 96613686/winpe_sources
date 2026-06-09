# Microsoft.Crm.Sandbox.WarmUpFailureWithFaultExceptionPlugin::Execute

- ea: `0xa280`
- end: `0xa2e8`
- name: `Microsoft.Crm.Sandbox.WarmUpFailureWithFaultExceptionPlugin::Execute`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xa280`

## pseudocode

```c

```

## disassembly

```asm
0xa280  ldarg.1
0xa281  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService
0xa286  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa28b  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xa290  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService
0xa295  stloc.0
0xa296  ldarg.1
0xa297  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0xa29c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa2a1  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xa2a6  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0xa2ab  ldloca.s 2
0xa2ad  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xa2b3  ldloc.2
0xa2b4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0xa2b9  ldstr    aOpportunity// "opportunity"
0xa2be  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0xa2c3  stloc.1
0xa2c4  ldloc.1
0xa2c5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0xa2ca  pop
0xa2cb  leave.s  loc_A2E7
0xa2cd  stloc.3
0xa2ce  ldloc.0
0xa2cf  ldstr    aSdkEx// "sdk ex: "
0xa2d4  ldloc.3
0xa2d5  call     string [mscorlib]System.String::Concat(object, object)
0xa2da  ldc.i4.0
0xa2db  newarr   [mscorlib]System.Object
0xa2e0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService::Trace(string, object[])
0xa2e5  rethrow
0xa2e7  ret
```
