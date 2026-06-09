# Microsoft.Crm.ServiceBus.RouterService::RetrieveClaims

- ea: `0x4090`
- end: `0x4114`
- name: `Microsoft.Crm.ServiceBus.RouterService::RetrieveClaims`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1b30`
- `0x4090`
- `0x42e0`
- `0x42f0`

## string_xrefs

- `0x40c8`: `RouterService.RetrieveClaims: `

## pseudocode

```c

```

## disassembly

```asm
0x4090  ldarg.0
0x4091  call     instance void Microsoft.Crm.ServiceBus.RouterService::AuthenticateCaller()
0x4096  ldarg.0
0x4097  ldarg.1
0x4098  call     instance string Microsoft.Crm.ServiceBus.RouterService::RetrieveClaimsInternal(class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x409d  stloc.0
0x409e  leave.s  loc_4112
0x40a0  stloc.1
0x40a1  ldarg.1
0x40a2  brtrue.s loc_40AB
0x40a4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40a9  br.s     loc_40B1
0x40ab  ldarg.1
0x40ac  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_OrganizationId()
0x40b1  stloc.2
0x40b2  ldloc.1
0x40b3  ldloc.2
0x40b4  ldc.i4.s 0x2F
0x40b6  ldstr    a0// "{0}"
0x40bb  ldc.i4.1
0x40bc  newarr   [mscorlib]System.Object
0x40c1  dup
0x40c2  ldc.i4.0
0x40c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40c8  ldstr    aRouterserviceR// "RouterService.RetrieveClaims: "
0x40cd  ldc.i4.1
0x40ce  newarr   [mscorlib]System.Object
0x40d3  dup
0x40d4  ldc.i4.0
0x40d5  ldloc.1
0x40d6  stelem.ref
0x40d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x40dc  stelem.ref
0x40dd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x40e2  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter Microsoft.Crm.ServiceBus.RouterService::_exceptionConverter
0x40e7  ldloc.1
0x40e8  ldc.i4.1
0x40e9  ldloca.s 3
0x40eb  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToFaultException(class [mscorlib]System.Exception, bool, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0x40f0  brfalse.s loc_40F4
0x40f2  ldloc.3
0x40f3  throw
0x40f4  ldloc.1
0x40f5  ldloc.2
0x40f6  ldc.i4.s 0x2F
0x40f8  ldstr    a0// "{0}"
0x40fd  ldc.i4.1
0x40fe  newarr   [mscorlib]System.Object
0x4103  dup
0x4104  ldc.i4.0
0x4105  ldstr    aUnexpectedExce// "UNEXPECTED: exception not converted"
0x410a  stelem.ref
0x410b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4110  rethrow
0x4112  ldloc.0
0x4113  ret
```
