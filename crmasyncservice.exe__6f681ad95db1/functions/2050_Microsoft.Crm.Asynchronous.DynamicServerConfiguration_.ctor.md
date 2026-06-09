# Microsoft.Crm.Asynchronous.DynamicServerConfiguration::.ctor

- ea: `0x2050`
- end: `0x2093`
- name: `Microsoft.Crm.Asynchronous.DynamicServerConfiguration::.ctor`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2010`

## callees

- `0x20d0`

## pseudocode

```c

```

## disassembly

```asm
0x2050  ldarg.0
0x2051  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IOrgMonitoringFilter>::.ctor()
0x2056  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IOrgMonitoringFilter> Microsoft.Crm.Asynchronous.DynamicServerConfiguration::_filters
0x205b  ldarg.0
0x205c  ldarg.1
0x205d  ldarg.2
0x205e  ldarg.3
0x205f  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ServerConfiguration::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueStatisticsHelper, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext)
0x2064  ldarg.0
0x2065  call     instance void Microsoft.Crm.Asynchronous.DynamicServerConfiguration::InitializeFilters()
0x206a  ldarg.0
0x206b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::.ctor()
0x2070  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.DynamicServerConfiguration::_organizationsToProcess
0x2075  ldarg.0
0x2076  ldarg.2
0x2077  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncBacklogAnalyzer::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueStatisticsHelper)
0x207c  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncBacklogAnalyzer Microsoft.Crm.Asynchronous.DynamicServerConfiguration::backlogAnalyzer
0x2081  ldarg.0
0x2082  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncBacklogAnalyzer Microsoft.Crm.Asynchronous.DynamicServerConfiguration::backlogAnalyzer
0x2087  ldarg.0
0x2088  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ServerConfiguration::get_AllOrganizationsToMonitor()
0x208d  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncBacklogAnalyzer::Monitor(class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>)
0x2092  ret
```
