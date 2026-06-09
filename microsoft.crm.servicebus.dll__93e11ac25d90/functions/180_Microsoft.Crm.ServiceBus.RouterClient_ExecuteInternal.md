# Microsoft.Crm.ServiceBus.RouterClient::ExecuteInternal

- ea: `0x180`
- end: `0x1c8`
- name: `Microsoft.Crm.ServiceBus.RouterClient::ExecuteInternal`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x120`

## callees

- `0x180`
- `0x1700`
- `0x17f0`
- `0x1800`
- `0x1860`

## pseudocode

```c

```

## disassembly

```asm
0x180  ldarg.0
0x181  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x186  ldstr    aRouterchannel// "RouterChannel"
0x18b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x190  ldarg.0
0x191  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x196  ldarg.1
0x197  ldarg.2
0x198  callvirt instance string Microsoft.Crm.ServiceBus.IRouterContract::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context, class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x19d  stloc.0
0x19e  leave.s  loc_1C6
0x1a0  pop
0x1a1  call     class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::get_Current()
0x1a6  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::get_RouterRequestTimeout()
0x1ab  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x1b0  pop
0x1b1  rethrow
0x1b3  pop
0x1b4  call     class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::get_Current()
0x1b9  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::get_RouterRequestFaulted()
0x1be  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x1c3  pop
0x1c4  rethrow
0x1c6  ldloc.0
0x1c7  ret
```
