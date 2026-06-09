# Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::Execute

- ea: `0x4940`
- end: `0x4976`
- name: `Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::Execute`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1700`
- `0x1820`
- `0x46a0`
- `0x4940`

## pseudocode

```c

```

## disassembly

```asm
0x4940  ldarg.0
0x4941  ldfld    class Microsoft.Crm.ServiceBus.IServiceBusChannel Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::channel
0x4946  ldarg.1
0x4947  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IServiceEndpointPlugin::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext)
0x494c  ldnull
0x494d  stloc.0
0x494e  leave.s  loc_4974
0x4950  pop
0x4951  call     class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::get_Current()
0x4956  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::get_AppFabricRequestTimeout()
0x495b  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x4960  pop
0x4961  ldarg.0
0x4962  ldc.i4.2
0x4963  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4968  rethrow
0x496a  pop
0x496b  ldarg.0
0x496c  ldc.i4.2
0x496d  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_Status(valuetype Microsoft.Crm.ServiceBus.ClientStatus value)
0x4972  rethrow
0x4974  ldloc.0
0x4975  ret
```
