# Microsoft.Crm.Reporting.RuntimeReportServer::GetExceptionErrorCode

- ea: `0x74c0`
- end: `0x74fc`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::GetExceptionErrorCode`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x7130`
- `0x72d0`

## callees

- `0x74c0`
- `0x7500`

## string_xrefs

- `0x74d6`: `rsDataExtensionNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x74c0  ldarg.0
0x74c1  ldarg.1
0x74c2  ldstr    aRssandboxing// "rsSandboxing"
0x74c7  call     instance bool Microsoft.Crm.Reporting.RuntimeReportServer::ReportExceptionDetailContainsErrorCode(class [System.Web.Services]System.Web.Services.Protocols.SoapException exception, string errorCode)
0x74cc  brfalse.s loc_74D4
0x74ce  ldc.i4   0x80048293
0x74d3  ret
0x74d4  ldarg.0
0x74d5  ldarg.1
0x74d6  ldstr    aRsdataextensio// "rsDataExtensionNotFound"
0x74db  call     instance bool Microsoft.Crm.Reporting.RuntimeReportServer::ReportExceptionDetailContainsErrorCode(class [System.Web.Services]System.Web.Services.Protocols.SoapException exception, string errorCode)
0x74e0  brtrue.s loc_74F0
0x74e2  ldarg.0
0x74e3  ldarg.1
0x74e4  ldstr    aRserrorloading// "rsErrorLoadingCodeModule"
0x74e9  call     instance bool Microsoft.Crm.Reporting.RuntimeReportServer::ReportExceptionDetailContainsErrorCode(class [System.Web.Services]System.Web.Services.Protocols.SoapException exception, string errorCode)
0x74ee  brfalse.s loc_74F6
0x74f0  ldc.i4   0x80048292
0x74f5  ret
0x74f6  ldc.i4   0x80048298
0x74fb  ret
```
