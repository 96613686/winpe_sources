# Microsoft.Crm.ServiceBus.ServiceBusUtility::TryHandleMaxMessageSize

- ea: `0x2820`
- end: `0x294c`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::TryHandleMaxMessageSize`
- size: `300`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x50e0`
- `0x6c10`

## callees

- `0x1450`
- `0x15d0`
- `0x1660`
- `0x1680`
- `0x2700`
- `0x2820`

## string_xrefs

- `0x286b`: `RemoteExecutionContext exceeded max allowed message size. Message will be sent but some information may be lost. Actual Size: {0} bytes, Max Size: {1} bytes for OrganizationId:{2}, serviceEndpointId: {3}, name: {4}, contract: {5}`
- `0x28dd`: `RemoteExecutionContext exceeded max allowed message size event after reducing size. Message will not be sent. Actual Size: {0} bytes, Max Size: {1} bytes for OrganizationId:{2}, serviceEndpointId: {3}, name: {4}`

## pseudocode

```c

```

## disassembly

```asm
0x2820  ldarg.0
0x2821  ldarg.2
0x2822  callvirt instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_MessageFormat()
0x2827  ldarg.0
0x2828  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x282d  ldarg.3
0x282e  call     int64 Microsoft.Crm.ServiceBus.ServiceBusUtility::GetObjectSize(object obj, valuetype MessageFormatType messageFormat, valuetype [mscorlib]System.Guid organizationId, [out] string& serializedObject)
0x2833  stloc.0
0x2834  ldloc.0
0x2835  ldarg.1
0x2836  ble      loc_294A
0x283b  ldarg.0
0x283c  ldnull
0x283d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_ParentContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext)
0x2842  ldarg.0
0x2843  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_InputParameters()
0x2848  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Clear()
0x284d  ldarg.0
0x284e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_PreEntityImages()
0x2853  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Clear()
0x2858  ldarg.0
0x2859  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_PostEntityImages()
0x285e  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Clear()
0x2863  ldarg.0
0x2864  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x2869  ldc.i4.s 0x40
0x286b  ldstr    aRemoteexecutio// "RemoteExecutionContext exceeded max all"...
0x2870  ldc.i4.6
0x2871  newarr   [mscorlib]System.Object
0x2876  dup
0x2877  ldc.i4.0
0x2878  ldloc.0
0x2879  box      [mscorlib]System.Int64
0x287e  stelem.ref
0x287f  dup
0x2880  ldc.i4.1
0x2881  ldarg.1
0x2882  box      [mscorlib]System.Int64
0x2887  stelem.ref
0x2888  dup
0x2889  ldc.i4.2
0x288a  ldarg.0
0x288b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x2890  box      [mscorlib]System.Guid
0x2895  stelem.ref
0x2896  dup
0x2897  ldc.i4.3
0x2898  ldarg.2
0x2899  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_ServiceEndpointId()
0x289e  stelem.ref
0x289f  dup
0x28a0  ldc.i4.4
0x28a1  ldarg.2
0x28a2  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Name()
0x28a7  stelem.ref
0x28a8  dup
0x28a9  ldc.i4.5
0x28aa  ldarg.2
0x28ab  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Contract()
0x28b0  box      ContractType
0x28b5  stelem.ref
0x28b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28bb  ldarg.0
0x28bc  ldarg.2
0x28bd  callvirt instance valuetype MessageFormatType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_MessageFormat()
0x28c2  ldarg.0
0x28c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x28c8  ldarg.3
0x28c9  call     int64 Microsoft.Crm.ServiceBus.ServiceBusUtility::GetObjectSize(object obj, valuetype MessageFormatType messageFormat, valuetype [mscorlib]System.Guid organizationId, [out] string& serializedObject)
0x28ce  stloc.0
0x28cf  ldloc.0
0x28d0  ldarg.1
0x28d1  ble.s    loc_2948
0x28d3  ldarg.2
0x28d4  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Contract()
0x28d9  ldc.i4.8
0x28da  ceq
0x28dc  stloc.1
0x28dd  ldstr    aRemoteexecutio_0// "RemoteExecutionContext exceeded max all"...
0x28e2  ldc.i4.5
0x28e3  newarr   [mscorlib]System.Object
0x28e8  dup
0x28e9  ldc.i4.0
0x28ea  ldloc.0
0x28eb  box      [mscorlib]System.Int64
0x28f0  stelem.ref
0x28f1  dup
0x28f2  ldc.i4.1
0x28f3  ldarg.1
0x28f4  box      [mscorlib]System.Int64
0x28f9  stelem.ref
0x28fa  dup
0x28fb  ldc.i4.2
0x28fc  ldarg.0
0x28fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x2902  box      [mscorlib]System.Guid
0x2907  stelem.ref
0x2908  dup
0x2909  ldc.i4.3
0x290a  ldarg.2
0x290b  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_ServiceEndpointId()
0x2910  stelem.ref
0x2911  dup
0x2912  ldc.i4.4
0x2913  ldarg.2
0x2914  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Name()
0x2919  stelem.ref
0x291a  call     string [mscorlib]System.String::Format(string, object[])
0x291f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2924  ldloc.1
0x2925  brtrue.s loc_292E
0x2927  ldc.i4   0x80050208
0x292c  br.s     loc_2933
0x292e  ldc.i4   0x80050207
0x2933  ldloc.1
0x2934  brtrue.s loc_293A
0x2936  ldc.i4.s 0x2F
0x2938  br.s     loc_293C
0x293a  ldc.i4.s 0x40
0x293c  ldc.i4.0
0x293d  newarr   [mscorlib]System.Object
0x2942  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, object[])
0x2947  throw
0x2948  ldc.i4.1
0x2949  ret
0x294a  ldc.i4.0
0x294b  ret
```
