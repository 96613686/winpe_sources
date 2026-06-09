# Microsoft.Crm.Reporting.SetupReportServer::CreateCrmBrowserRole

- ea: `0x7cc0`
- end: `0x7cfd`
- name: `Microsoft.Crm.Reporting.SetupReportServer::CreateCrmBrowserRole`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7710`
- `0x7f90`
- `0x8340`

## callees

- `0x4870`
- `0x7980`
- `0x7cc0`
- `0x7d00`
- `0x8230`

## pseudocode

```c

```

## disassembly

```asm
0x7cc0  ldarg.0
0x7cc1  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7cc6  ldstr    aSrsCrmbrowserr// "SRS.CrmBrowserRole"
0x7ccb  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7cd0  stloc.0
0x7cd1  ldarg.0
0x7cd2  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7cd7  ldstr    aSrsCrmbrowserd// "SRS.CrmBrowserDescription"
0x7cdc  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x7ce1  stloc.1
0x7ce2  ldarg.0
0x7ce3  ldloc.0
0x7ce4  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::RoleExists(string roleName)
0x7ce9  brfalse.s loc_7CEC
0x7ceb  ret
0x7cec  ldarg.0
0x7ced  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Reporting.CrmTask> Microsoft.Crm.Reporting.SetupReportServer::GetCrmBrowserRoleTasks()
0x7cf2  stloc.2
0x7cf3  ldarg.0
0x7cf4  ldloc.0
0x7cf5  ldloc.1
0x7cf6  ldloc.2
0x7cf7  callvirt instance void Microsoft.Crm.Reporting.SetupReportServer::CreateRole(string name, string description, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Reporting.CrmTask> roleTasks)
0x7cfc  ret
```
