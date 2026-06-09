# Microsoft.Crm.Reporting.SetupReportServer::CreateCrmPublisherRole

- ea: `0x7dc0`
- end: `0x7f57`
- name: `Microsoft.Crm.Reporting.SetupReportServer::CreateCrmPublisherRole`
- size: `407`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7f90`
- `0x8340`

## callees

- `0x130`
- `0x150`
- `0x160`
- `0x4870`
- `0x7980`
- `0x7d00`
- `0x7dc0`
- `0x8230`

## string_xrefs

- `0x7e00`: `SRS.TaskCreateLinkedReport`
- `0x7e30`: `SRS.TaskManageDataSource`
- `0x7e62`: `SRS.TaskManageFolder`
- `0x7e94`: `SRS.TaskManageReports`
- `0x7ec6`: `SRS.TaskManageResource`
- `0x7ef8`: `SRS.TaskSetItemSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x7dc0  ldarg.0
0x7dc1  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7dc6  ldstr    aSrsCrmpublishe// "SRS.CrmPublisherRole"
0x7dcb  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7dd0  stloc.0
0x7dd1  ldarg.0
0x7dd2  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7dd7  ldstr    aSrsCrmpublishe_0// "SRS.CrmPublisherDescription"
0x7ddc  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7de1  stloc.1
0x7de2  ldarg.0
0x7de3  ldloc.0
0x7de4  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::RoleExists(string roleName)
0x7de9  brfalse.s loc_7DEC
0x7deb  ret
0x7dec  ldarg.0
0x7ded  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Reporting.CrmTask> Microsoft.Crm.Reporting.SetupReportServer::GetCrmBrowserRoleTasks()
0x7df2  stloc.2
0x7df3  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7df8  stloc.3
0x7df9  ldloc.3
0x7dfa  ldarg.0
0x7dfb  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7e00  ldstr    aSrsTaskcreatel// "SRS.TaskCreateLinkedReport"
0x7e05  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7e0a  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7e0f  ldloc.3
0x7e10  ldstr    a3246fdf716fb48// "3246FDF7-16FB-4802-ABFA-76D4F4A8AD62"
0x7e15  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7e1a  ldloc.2
0x7e1b  ldloc.3
0x7e1c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7e21  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7e26  stloc.s  4
0x7e28  ldloc.s  4
0x7e2a  ldarg.0
0x7e2b  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7e30  ldstr    aSrsTaskmanaged// "SRS.TaskManageDataSource"
0x7e35  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7e3a  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7e3f  ldloc.s  4
0x7e41  ldstr    aAd4523ad09b646// "AD4523AD-09B6-46ab-A7F0-AD1F52449FE1"
0x7e46  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7e4b  ldloc.2
0x7e4c  ldloc.s  4
0x7e4e  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7e53  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7e58  stloc.s  5
0x7e5a  ldloc.s  5
0x7e5c  ldarg.0
0x7e5d  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7e62  ldstr    aSrsTaskmanagef// "SRS.TaskManageFolder"
0x7e67  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7e6c  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7e71  ldloc.s  5
0x7e73  ldstr    a683665abEe4b40// "683665AB-EE4B-4026-99AE-68A9899F8B6E"
0x7e78  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7e7d  ldloc.2
0x7e7e  ldloc.s  5
0x7e80  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7e85  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7e8a  stloc.s  6
0x7e8c  ldloc.s  6
0x7e8e  ldarg.0
0x7e8f  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7e94  ldstr    aSrsTaskmanager// "SRS.TaskManageReports"
0x7e99  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7e9e  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7ea3  ldloc.s  6
0x7ea5  ldstr    a88552a2499ba46// "88552A24-99BA-46ab-90CD-EF66FD3E444D"
0x7eaa  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7eaf  ldloc.2
0x7eb0  ldloc.s  6
0x7eb2  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7eb7  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7ebc  stloc.s  7
0x7ebe  ldloc.s  7
0x7ec0  ldarg.0
0x7ec1  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7ec6  ldstr    aSrsTaskmanager_0// "SRS.TaskManageResource"
0x7ecb  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7ed0  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7ed5  ldloc.s  7
0x7ed7  ldstr    a1d574e69B01d42// "1D574E69-B01D-4278-A25A-DEE6B3790F81"
0x7edc  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7ee1  ldloc.2
0x7ee2  ldloc.s  7
0x7ee4  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7ee9  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7eee  stloc.s  8
0x7ef0  ldloc.s  8
0x7ef2  ldarg.0
0x7ef3  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7ef8  ldstr    aSrsTasksetitem// "SRS.TaskSetItemSecurity"
0x7efd  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7f02  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7f07  ldloc.s  8
0x7f09  ldstr    aE96a7928F3a540// "E96A7928-F3A5-409d-A6AA-0808172B28CB"
0x7f0e  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7f13  ldloc.2
0x7f14  ldloc.s  8
0x7f16  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7f1b  newobj   instance void Microsoft.Crm.Reporting.CrmTask::.ctor()
0x7f20  stloc.s  9
0x7f22  ldloc.s  9
0x7f24  ldarg.0
0x7f25  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7f2a  ldstr    aSrsManagerepor// "SRS.ManageReportHistory"
0x7f2f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7f34  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_Name(string value)
0x7f39  ldloc.s  9
0x7f3b  ldstr    a75d856b82fc141// "75D856B8-2FC1-41c9-8DFA-FE0FF6153C20"
0x7f40  callvirt instance void Microsoft.Crm.Reporting.CrmTask::set_TaskId(string value)
0x7f45  ldloc.2
0x7f46  ldloc.s  9
0x7f48  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::Add(var<u1>)
0x7f4d  ldarg.0
0x7f4e  ldloc.0
0x7f4f  ldloc.1
0x7f50  ldloc.2
0x7f51  callvirt instance void Microsoft.Crm.Reporting.SetupReportServer::CreateRole(string name, string description, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Reporting.CrmTask> roleTasks)
0x7f56  ret
```
