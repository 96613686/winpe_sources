# Microsoft.Crm.Reporting.RuntimeReportServer::DeleteReport

- ea: `0x5950`
- end: `0x597d`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::DeleteReport`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x4a20`
- `0x5950`

## pseudocode

```c

```

## disassembly

```asm
0x5950  ldarg.1
0x5951  ldstr    aReportid_0// "reportId"
0x5956  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x595b  ldarg.2
0x595c  brfalse.s loc_595F
0x595e  ret
0x595f  ldarg.0
0x5960  ldarg.0
0x5961  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x5966  ldarga.s 1
0x5968  ldstr    aB// "B"
0x596d  call     instance string [mscorlib]System.Guid::ToString(string)
0x5972  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string)
0x5977  call     instance void Microsoft.Crm.Reporting.ReportServer::DeleteItem(string path)
0x597c  ret
```
