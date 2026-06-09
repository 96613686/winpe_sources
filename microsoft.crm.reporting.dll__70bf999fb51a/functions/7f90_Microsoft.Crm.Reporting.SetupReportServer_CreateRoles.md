# Microsoft.Crm.Reporting.SetupReportServer::CreateRoles

- ea: `0x7f90`
- end: `0x7f9d`
- name: `Microsoft.Crm.Reporting.SetupReportServer::CreateRoles`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x75b0`

## callees

- `0x7cc0`
- `0x7dc0`

## pseudocode

```c

```

## disassembly

```asm
0x7f90  ldarg.0
0x7f91  call     instance void Microsoft.Crm.Reporting.SetupReportServer::CreateCrmBrowserRole()
0x7f96  ldarg.0
0x7f97  call     instance void Microsoft.Crm.Reporting.SetupReportServer::CreateCrmPublisherRole()
0x7f9c  ret
```
