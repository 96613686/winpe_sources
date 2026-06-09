# Microsoft.Crm.Asynchronous.AsyncService::EnableOptionalFeatures

- ea: `0x1040`
- end: `0x1086`
- name: `Microsoft.Crm.Asynchronous.AsyncService::EnableOptionalFeatures`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`

## callees

- `0x1040`
- `0x1090`
- `0xa3f0`

## pseudocode

```c

```

## disassembly

```asm
0x1040  newobj   instance void Microsoft.Crm.Asynchronous.Bridges.CrmRegistry::.ctor()
0x1045  ldnull
0x1046  newobj   instance void [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Flighting.MasterRegKeyFlightClient::.ctor(class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.ICrmRegistry, class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Flighting.IFlightClient)
0x104b  ldstr    aAsyncwebapi// "asyncwebapi"
0x1050  ldnull
0x1051  callvirt instance bool [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Flighting.MasterRegKeyFlightClient::IsFeatureEnabled(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x1056  brfalse.s loc_105F
0x1058  ldarg.0
0x1059  ldarg.1
0x105a  call     instance void Microsoft.Crm.Asynchronous.AsyncService::ConfigureWebApp(class [Autofac]Autofac.ContainerBuilder builder)
0x105f  leave.s  loc_1085
0x1061  stloc.0
0x1062  ldloc.0
0x1063  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1068  ldc.i4.s 0x15
0x106a  ldstr    aFailedToEnable// "Failed to enable an optional Async feat"...
0x106f  ldc.i4.1
0x1070  newarr   [mscorlib]System.Object
0x1075  dup
0x1076  ldc.i4.0
0x1077  ldloc.0
0x1078  callvirt instance string [mscorlib]System.Object::ToString()
0x107d  stelem.ref
0x107e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1083  leave.s  loc_1085
0x1085  ret
```
