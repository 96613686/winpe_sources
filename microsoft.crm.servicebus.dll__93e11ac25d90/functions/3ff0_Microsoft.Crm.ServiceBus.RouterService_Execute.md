# Microsoft.Crm.ServiceBus.RouterService::Execute

- ea: `0x3ff0`
- end: `0x4085`
- name: `Microsoft.Crm.ServiceBus.RouterService::Execute`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1700`
- `0x1810`
- `0x1b30`
- `0x3ff0`
- `0x4120`
- `0x42f0`

## string_xrefs

- `0x4039`: `RouterService.Execute: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3ff0  call     class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::get_Current()
0x3ff5  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::get_RouterRequestReceived()
0x3ffa  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x3fff  pop
0x4000  ldarg.0
0x4001  call     instance void Microsoft.Crm.ServiceBus.RouterService::AuthenticateCaller()
0x4006  ldarg.0
0x4007  ldarg.1
0x4008  ldarg.2
0x4009  call     instance string Microsoft.Crm.ServiceBus.RouterService::ExecuteInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context, class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x400e  stloc.0
0x400f  leave.s  loc_4083
0x4011  stloc.1
0x4012  ldarg.2
0x4013  brtrue.s loc_401C
0x4015  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x401a  br.s     loc_4022
0x401c  ldarg.2
0x401d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_OrganizationId()
0x4022  stloc.2
0x4023  ldloc.1
0x4024  ldloc.2
0x4025  ldc.i4.s 0x2F
0x4027  ldstr    a0// "{0}"
0x402c  ldc.i4.1
0x402d  newarr   [mscorlib]System.Object
0x4032  dup
0x4033  ldc.i4.0
0x4034  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4039  ldstr    aRouterserviceE// "RouterService.Execute: {0}"
0x403e  ldc.i4.1
0x403f  newarr   [mscorlib]System.Object
0x4044  dup
0x4045  ldc.i4.0
0x4046  ldloc.1
0x4047  stelem.ref
0x4048  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x404d  stelem.ref
0x404e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4053  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter Microsoft.Crm.ServiceBus.RouterService::_exceptionConverter
0x4058  ldloc.1
0x4059  ldc.i4.1
0x405a  ldloca.s 3
0x405c  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToFaultException(class [mscorlib]System.Exception, bool, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0x4061  brfalse.s loc_4065
0x4063  ldloc.3
0x4064  throw
0x4065  ldloc.1
0x4066  ldloc.2
0x4067  ldc.i4.s 0x2F
0x4069  ldstr    a0// "{0}"
0x406e  ldc.i4.1
0x406f  newarr   [mscorlib]System.Object
0x4074  dup
0x4075  ldc.i4.0
0x4076  ldstr    aUnexpectedExce// "UNEXPECTED: exception not converted"
0x407b  stelem.ref
0x407c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4081  rethrow
0x4083  ldloc.0
0x4084  ret
```
