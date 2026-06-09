# Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::Execute

- ea: `0x4c90`
- end: `0x4d0b`
- name: `Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::Execute`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1700`
- `0x1820`
- `0x46a0`
- `0x4c90`

## pseudocode

```c

```

## disassembly

```asm
0x4c90  ldarg.0
0x4c91  ldfld    class Microsoft.Crm.ServiceBus.ITwoWayServiceBusChannel Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::channel
0x4c96  ldarg.1
0x4c97  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITwoWayServiceEndpointPlugin::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext)
0x4c9c  stloc.0
0x4c9d  leave.s  loc_4D09
0x4c9f  ldarg.0
0x4ca0  ldc.i4.2
0x4ca1  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4ca6  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ServiceEndpointFault>::get_Detail()
0x4cab  stloc.1
0x4cac  ldloc.1
0x4cad  brfalse.s loc_4CE3
0x4caf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::.ctor()
0x4cb4  dup
0x4cb5  ldc.i4   0x80040265
0x4cba  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_ErrorCode(int32)
0x4cbf  dup
0x4cc0  ldloc.1
0x4cc1  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ServiceEndpointFault::get_Message()
0x4cc6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_Message(string)
0x4ccb  dup
0x4ccc  ldloc.1
0x4ccd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ServiceEndpointFault::get_ErrorDetails()
0x4cd2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_ErrorDetails(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection)
0x4cd7  dup
0x4cd8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x4cdd  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::.ctor(var<u1>, !!T0)
0x4ce2  throw
0x4ce3  rethrow
0x4ce5  pop
0x4ce6  call     class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::get_Current()
0x4ceb  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::get_AppFabricRequestTimeout()
0x4cf0  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x4cf5  pop
0x4cf6  ldarg.0
0x4cf7  ldc.i4.2
0x4cf8  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4cfd  rethrow
0x4cff  pop
0x4d00  ldarg.0
0x4d01  ldc.i4.2
0x4d02  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4d07  rethrow
0x4d09  ldloc.0
0x4d0a  ret
```
