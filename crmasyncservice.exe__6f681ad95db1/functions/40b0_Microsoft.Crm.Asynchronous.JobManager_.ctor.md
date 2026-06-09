# Microsoft.Crm.Asynchronous.JobManager::.ctor

- ea: `0x40b0`
- end: `0x40f7`
- name: `Microsoft.Crm.Asynchronous.JobManager::.ctor`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe0`

## string_xrefs

- `0x40c9`: `dataAccessFactory`
- `0x40d5`: `config`

## pseudocode

```c

```

## disassembly

```asm
0x40b0  ldarg.0
0x40b1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40b6  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.JobManager::_scaleGroupId
0x40bb  ldarg.0
0x40bc  ldarg.1
0x40bd  ldarg.2
0x40be  ldarg.s  6
0x40c0  ldarg.s  7
0x40c2  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::.ctor(string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandler, class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog)
0x40c7  ldarg.s  5
0x40c9  ldstr    aDataaccessfact// "dataAccessFactory"
0x40ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x40d3  ldarg.s  4
0x40d5  ldstr    aConfig// "config"
0x40da  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x40df  ldarg.0
0x40e0  ldarg.s  4
0x40e2  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::_config
0x40e7  ldarg.0
0x40e8  ldarg.s  5
0x40ea  stfld    class Microsoft.Crm.Asynchronous.IJobDataAccessFactory Microsoft.Crm.Asynchronous.JobManager::_dataAccessFactory
0x40ef  ldarg.0
0x40f0  ldarg.3
0x40f1  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueuePerformanceCounters Microsoft.Crm.Asynchronous.JobManager::_counters
0x40f6  ret
```
