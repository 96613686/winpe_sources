# Microsoft.Crm.Asynchronous.DynamicServerConfiguration::InitializeFilters

- ea: `0x20d0`
- end: `0x20e2`
- name: `Microsoft.Crm.Asynchronous.DynamicServerConfiguration::InitializeFilters`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2050`

## callees

- `0x5270`

## pseudocode

```c

```

## disassembly

```asm
0x20d0  ldarg.0
0x20d1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IOrgMonitoringFilter> Microsoft.Crm.Asynchronous.DynamicServerConfiguration::_filters
0x20d6  ldc.i4.1
0x20d7  newobj   instance void Microsoft.Crm.Asynchronous.TopNBacklogOrganizationsFilter::.ctor(int32 count)
0x20dc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IOrgMonitoringFilter>::Add(var<u1>)
0x20e1  ret
```
