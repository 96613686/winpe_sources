# Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException

- ea: `0x4960`
- end: `0x496e`
- name: `Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException`
- size: `14`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7980`
- `0x7a50`
- `0x7af0`
- `0x8030`
- `0x8160`
- `0x8230`
- `0x8510`

## callees

- `0x4970`

## pseudocode

```c

```

## disassembly

```asm
0x4960  ldarg.0
0x4961  ldarg.1
0x4962  ldarg.2
0x4963  ldc.i4   0x80048300
0x4968  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x496d  ret
```
