# Microsoft.Crm.ServiceBus.ServiceBusRestClient::Execute

- ea: `0x4ab0`
- end: `0x4b41`
- name: `Microsoft.Crm.ServiceBus.ServiceBusRestClient::Execute`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1700`
- `0x1820`
- `0x46a0`
- `0x4ab0`

## pseudocode

```c

```

## disassembly

```asm
0x4ab0  ldarg.0
0x4ab1  ldfld    class Microsoft.Crm.ServiceBus.IWebHttpServiceBusChannel Microsoft.Crm.ServiceBus.ServiceBusRestClient::channel
0x4ab6  newobj   instance void [System.ServiceModel]System.ServiceModel.OperationContextScope::.ctor(class [System.ServiceModel]System.ServiceModel.IContextChannel)
0x4abb  stloc.0
0x4abc  ldarg.0
0x4abd  ldfld    class Microsoft.Crm.ServiceBus.IWebHttpServiceBusChannel Microsoft.Crm.ServiceBus.ServiceBusRestClient::channel
0x4ac2  ldarg.1
0x4ac3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IWebHttpServiceEndpointPlugin::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext)
0x4ac8  stloc.1
0x4ac9  leave.s  loc_4B3F
0x4acb  ldloc.0
0x4acc  brfalse.s loc_4AD4
0x4ace  ldloc.0
0x4acf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ad4  endfinally
0x4ad5  ldarg.0
0x4ad6  ldc.i4.2
0x4ad7  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4adc  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ServiceEndpointFault>::get_Detail()
0x4ae1  stloc.2
0x4ae2  ldloc.2
0x4ae3  brfalse.s loc_4B19
0x4ae5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::.ctor()
0x4aea  dup
0x4aeb  ldc.i4   0x80040265
0x4af0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_ErrorCode(int32)
0x4af5  dup
0x4af6  ldloc.2
0x4af7  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ServiceEndpointFault::get_Message()
0x4afc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_Message(string)
0x4b01  dup
0x4b02  ldloc.2
0x4b03  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ServiceEndpointFault::get_ErrorDetails()
0x4b08  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_ErrorDetails(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection)
0x4b0d  dup
0x4b0e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x4b13  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::.ctor(var<u1>, !!T0)
0x4b18  throw
0x4b19  rethrow
0x4b1b  pop
0x4b1c  call     class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::get_Current()
0x4b21  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::get_AppFabricRequestTimeout()
0x4b26  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x4b2b  pop
0x4b2c  ldarg.0
0x4b2d  ldc.i4.2
0x4b2e  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4b33  rethrow
0x4b35  pop
0x4b36  ldarg.0
0x4b37  ldc.i4.2
0x4b38  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4b3d  rethrow
0x4b3f  ldloc.1
0x4b40  ret
```
