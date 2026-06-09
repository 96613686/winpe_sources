# Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::ReportQueryPerformance

- ea: `0x4da70`
- end: `0x4db04`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::ReportQueryPerformance`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x2f290`
- `0x2f350`
- `0x2f3b0`
- `0x4da70`
- `0x4db10`

## string_xrefs

- `0x4da7a`: `_Read`
- `0x4da82`: `_Update`
- `0x4dabd`: `ConfigDBAverageQueryTime`
- `0x4dac9`: `ConfigDBAverageQueryTime`
- `0x4dad5`: `ConfigDBQueryCount`
- `0x4dae1`: `ConfigDBQueryCount`
- `0x4daec`: `ConfigDBQueriesPerSecond`
- `0x4daf8`: `ConfigDBQueriesPerSecond`

## pseudocode

```c

```

## disassembly

```asm
0x4da70  call     void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::LoadPerfCounters()
0x4da75  ldnull
0x4da76  stloc.0
0x4da77  ldarg.3
0x4da78  brfalse.s loc_4DA82
0x4da7a  ldstr    aRead// "_Read"
0x4da7f  stloc.0
0x4da80  br.s     loc_4DA88
0x4da82  ldstr    aUpdate_1// "_Update"
0x4da87  stloc.0
0x4da88  ldarg.s  4
0x4da8a  brfalse.s loc_4DA9A
0x4da8c  ldloc.0
0x4da8d  ldstr    aSuccess_1// "_Success"
0x4da92  call     string [mscorlib]System.String::Concat(string, string)
0x4da97  stloc.0
0x4da98  br.s     loc_4DAA6
0x4da9a  ldloc.0
0x4da9b  ldstr    aFailed_0// "_Failed"
0x4daa0  call     string [mscorlib]System.String::Concat(string, string)
0x4daa5  stloc.0
0x4daa6  ldarg.2
0x4daa7  box      Microsoft.Crm.SharedDatabase.ConfigScope
0x4daac  ldstr    aG// "G"
0x4dab1  call     instance string [mscorlib]System.Enum::ToString(string)
0x4dab6  ldloc.0
0x4dab7  call     string [mscorlib]System.String::Concat(string, string)
0x4dabc  stloc.1
0x4dabd  ldstr    aConfigdbaverag// "ConfigDBAverageQueryTime"
0x4dac2  call     bool Microsoft.Crm.CrmPerformanceCounterFactory::Exists(string counterName)
0x4dac7  brfalse.s loc_4DAD5
0x4dac9  ldstr    aConfigdbaverag// "ConfigDBAverageQueryTime"
0x4dace  ldloc.1
0x4dacf  ldarg.1
0x4dad0  call     void Microsoft.Crm.CrmPerformanceCounterFactory::IncrementCounter(string counterName, string instanceName, int64 value)
0x4dad5  ldstr    aConfigdbqueryc// "ConfigDBQueryCount"
0x4dada  call     bool Microsoft.Crm.CrmPerformanceCounterFactory::Exists(string counterName)
0x4dadf  brfalse.s loc_4DAEC
0x4dae1  ldstr    aConfigdbqueryc// "ConfigDBQueryCount"
0x4dae6  ldloc.1
0x4dae7  call     void Microsoft.Crm.CrmPerformanceCounterFactory::IncrementCounter(string counterName, string instanceName)
0x4daec  ldstr    aConfigdbquerie// "ConfigDBQueriesPerSecond"
0x4daf1  call     bool Microsoft.Crm.CrmPerformanceCounterFactory::Exists(string counterName)
0x4daf6  brfalse.s loc_4DB03
0x4daf8  ldstr    aConfigdbquerie// "ConfigDBQueriesPerSecond"
0x4dafd  ldloc.1
0x4dafe  call     void Microsoft.Crm.CrmPerformanceCounterFactory::IncrementCounter(string counterName, string instanceName)
0x4db03  ret
```
