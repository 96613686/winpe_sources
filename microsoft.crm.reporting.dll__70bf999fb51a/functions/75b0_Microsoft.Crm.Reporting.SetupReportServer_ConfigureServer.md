# Microsoft.Crm.Reporting.SetupReportServer::ConfigureServer

- ea: `0x75b0`
- end: `0x75d8`
- name: `Microsoft.Crm.Reporting.SetupReportServer::ConfigureServer`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x75e0`
- `0x7920`
- `0x7b80`
- `0x7f90`

## pseudocode

```c

```

## disassembly

```asm
0x75b0  ldarg.0
0x75b1  ldc.i4.0
0x75b2  call     instance void Microsoft.Crm.Reporting.SetupReportServer::ValidateServerInternal(bool validateCallerPermission)
0x75b7  ldarg.0
0x75b8  call     instance void Microsoft.Crm.Reporting.SetupReportServer::CreateRoles()
0x75bd  ldarg.0
0x75be  ldarg.1
0x75bf  ldarg.2
0x75c0  ldarg.3
0x75c1  ldarg.s  4
0x75c3  ldarg.s  5
0x75c5  call     instance void Microsoft.Crm.Reporting.SetupReportServer::CreateCommonFolder(string organizationName, string sqlAccessGroupName, string reportingGroupName, string privilegeReportGroupName, string networkServiceAccount)
0x75ca  ldarg.0
0x75cb  ldarg.1
0x75cc  ldarg.2
0x75cd  ldarg.3
0x75ce  ldarg.s  4
0x75d0  ldarg.s  5
0x75d2  call     instance void Microsoft.Crm.Reporting.SetupReportServer::ConfigureOrganization(string organizationName, string sqlAccessGroupName, string reportingGroupName, string privilegeReportGroupName, string networkServiceAccount)
0x75d7  ret
```
