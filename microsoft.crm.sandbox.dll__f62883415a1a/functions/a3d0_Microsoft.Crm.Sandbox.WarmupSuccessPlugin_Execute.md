# Microsoft.Crm.Sandbox.WarmupSuccessPlugin::Execute

- ea: `0xa3d0`
- end: `0xa438`
- name: `Microsoft.Crm.Sandbox.WarmupSuccessPlugin::Execute`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xa3d0`

## pseudocode

```c

```

## disassembly

```asm
0xa3d0  ldarg.1
0xa3d1  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService
0xa3d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa3db  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xa3e0  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService
0xa3e5  stloc.0
0xa3e6  ldarg.1
0xa3e7  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0xa3ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa3f1  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xa3f6  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0xa3fb  ldloca.s 2
0xa3fd  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xa403  ldloc.2
0xa404  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0xa409  ldstr    aOpportunity// "opportunity"
0xa40e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0xa413  stloc.1
0xa414  ldloc.1
0xa415  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0xa41a  pop
0xa41b  leave.s  loc_A437
0xa41d  stloc.3
0xa41e  ldloc.0
0xa41f  ldstr    aSdkEx// "sdk ex: "
0xa424  ldloc.3
0xa425  call     string [mscorlib]System.String::Concat(object, object)
0xa42a  ldc.i4.0
0xa42b  newarr   [mscorlib]System.Object
0xa430  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService::Trace(string, object[])
0xa435  rethrow
0xa437  ret
```
