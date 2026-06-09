# Microsoft.Crm.Reporting.SetupReportServer::GrantBrowserAccess

- ea: `0x7710`
- end: `0x7752`
- name: `Microsoft.Crm.Reporting.SetupReportServer::GrantBrowserAccess`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4870`
- `0x7af0`
- `0x7cc0`

## pseudocode

```c

```

## disassembly

```asm
0x7710  ldarg.1
0x7711  ldstr    aAccountname// "accountName"
0x7716  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x771b  ldarg.0
0x771c  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7721  ldstr    aSrsCrmbrowserr// "SRS.CrmBrowserRole"
0x7726  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x772b  stloc.0
0x772c  ldarg.0
0x772d  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x7732  ldstr    aSrsCrmbrowserd// "SRS.CrmBrowserDescription"
0x7737  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x773c  stloc.1
0x773d  ldarg.0
0x773e  call     instance void Microsoft.Crm.Reporting.SetupReportServer::CreateCrmBrowserRole()
0x7743  ldarg.0
0x7744  ldarg.1
0x7745  ldloc.0
0x7746  ldloc.1
0x7747  ldstr    asc_C3C6// "/"
0x774c  call     instance void Microsoft.Crm.Reporting.SetupReportServer::AssignRole(string userGroup, string roleName, string roleDescription, string folderPath)
0x7751  ret
```
