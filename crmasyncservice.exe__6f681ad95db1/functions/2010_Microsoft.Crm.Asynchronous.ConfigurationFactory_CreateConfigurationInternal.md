# Microsoft.Crm.Asynchronous.ConfigurationFactory::CreateConfigurationInternal

- ea: `0x2010`
- end: `0x203d`
- name: `Microsoft.Crm.Asynchronous.ConfigurationFactory::CreateConfigurationInternal`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1fc0`

## callees

- `0xc60`
- `0x1910`
- `0x1fa0`
- `0x2010`
- `0x2050`

## pseudocode

```c

```

## disassembly

```asm
0x2010  call     bool Microsoft.Crm.Asynchronous.ConfigurationFactory::get_IsDynamicAsync()
0x2015  brtrue.s loc_202A
0x2017  ldarg.0
0x2018  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncService::get_OperationsFactory()
0x201d  ldarg.1
0x201e  ldarg.0
0x201f  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext Microsoft.Crm.Asynchronous.AsyncService::get_DebugContext()
0x2024  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ServerConfiguration::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueStatisticsHelper, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext)
0x2029  ret
0x202a  ldarg.0
0x202b  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncService::get_OperationsFactory()
0x2030  ldarg.1
0x2031  ldarg.0
0x2032  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext Microsoft.Crm.Asynchronous.AsyncService::get_DebugContext()
0x2037  newobj   instance void Microsoft.Crm.Asynchronous.DynamicServerConfiguration::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory operationsFactory, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueStatisticsHelper queueStatisticsHelper, [opt] class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext debugContext)
0x203c  ret
```
