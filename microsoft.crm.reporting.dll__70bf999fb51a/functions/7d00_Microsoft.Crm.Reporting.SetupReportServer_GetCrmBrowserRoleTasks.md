# Microsoft.Crm.Reporting.SetupReportServer::GetCrmBrowserRoleTasks

- ea: `0x7d00`
- end: `0x7dbe`
- name: `Microsoft.Crm.Reporting.SetupReportServer::GetCrmBrowserRoleTasks`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7cc0`
- `0x7dc0`

## callees

- `0x130`
- `0x150`
- `0x160`
- `0x4870`

## string_xrefs

- `0x7d12`: `SRS.TaskViewFolder`
- `0x7d40`: `SRS.TaskViewReport`
- `0x7d6e`: `SRS.TaskViewResource`
- `0x7d9c`: `SRS.TaskManageSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x7d00  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Reporting.CrmTask>::.ctor()
0x7d05  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7d0a  stloc.0
0x7d0b  ldloc.0
0x7d0c  ldarg.0
0x7d0d  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7d12  ldstr    aSrsTaskviewfol// "SRS.TaskViewFolder"
0x7d17  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7d1c  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7d21  ldloc.0
0x7d22  ldstr    a2fbf7ae50db646// "2FBF7AE5-0DB6-46f2-B9BB-480794FBC97E"
0x7d27  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7d2c  dup
0x7d2d  ldloc.0
0x7d2e  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7d33  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7d38  stloc.1
0x7d39  ldloc.1
0x7d3a  ldarg.0
0x7d3b  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7d40  ldstr    aSrsTaskviewrep// "SRS.TaskViewReport"
0x7d45  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7d4a  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7d4f  ldloc.1
0x7d50  ldstr    aE2723f22E29c49// "E2723F22-E29C-496b-B981-1D775F45FC09"
0x7d55  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7d5a  dup
0x7d5b  ldloc.1
0x7d5c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7d61  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7d66  stloc.2
0x7d67  ldloc.2
0x7d68  ldarg.0
0x7d69  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7d6e  ldstr    aSrsTaskviewres// "SRS.TaskViewResource"
0x7d73  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7d78  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7d7d  ldloc.2
0x7d7e  ldstr    a993c580b3fbf44// "993C580B-3FBF-444b-B85E-A8DA50ADF40F"
0x7d83  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7d88  dup
0x7d89  ldloc.2
0x7d8a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7d8f  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7d94  stloc.3
0x7d95  ldloc.3
0x7d96  ldarg.0
0x7d97  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7d9c  ldstr    aSrsTaskmanages// "SRS.TaskManageSubscription"
0x7da1  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7da6  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7dab  ldloc.3
0x7dac  ldstr    aF95f31d0834a4c// "F95F31D0-834A-4c0e-B290-E3E4477908CA"
0x7db1  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7db6  dup
0x7db7  ldloc.3
0x7db8  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7dbd  ret
```
