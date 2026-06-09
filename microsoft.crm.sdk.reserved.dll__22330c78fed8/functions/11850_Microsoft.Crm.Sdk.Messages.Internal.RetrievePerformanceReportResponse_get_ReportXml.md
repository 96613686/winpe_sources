# Microsoft.Crm.Sdk.Messages.Internal.RetrievePerformanceReportResponse::get_ReportXml

- ea: `0x11850`
- end: `0x1187a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrievePerformanceReportResponse::get_ReportXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11850`

## string_xrefs

- `0x11856`: `ReportXml`
- `0x11868`: `ReportXml`

## pseudocode

```c

```

## disassembly

```asm
0x11850  ldarg.0
0x11851  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11856  ldstr    aReportxml// "ReportXml"
0x1185b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11860  brfalse.s loc_11878
0x11862  ldarg.0
0x11863  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11868  ldstr    aReportxml// "ReportXml"
0x1186d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11872  castclass [mscorlib]System.String
0x11877  ret
0x11878  ldnull
0x11879  ret
```
