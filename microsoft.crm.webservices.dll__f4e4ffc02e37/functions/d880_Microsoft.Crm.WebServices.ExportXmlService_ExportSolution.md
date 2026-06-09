# Microsoft.Crm.WebServices.ExportXmlService::ExportSolution

- ea: `0xd880`
- end: `0xd8a5`
- name: `Microsoft.Crm.WebServices.ExportXmlService::ExportSolution`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xdab0`
- `0xdad0`

## callees

- `0xd8b0`

## pseudocode

```c

```

## disassembly

```asm
0xd880  ldarg.0
0xd881  ldarg.1
0xd882  ldarg.2
0xd883  ldsfld   string [mscorlib]System.String::Empty
0xd888  ldarg.3
0xd889  ldarg.s  4
0xd88b  ldarg.s  5
0xd88d  ldarg.s  6
0xd88f  ldarg.s  7
0xd891  ldarg.s  8
0xd893  ldarg.s  9
0xd895  ldarg.s  0xA
0xd897  ldarg.s  0xB
0xd899  ldarg.s  0xC
0xd89b  ldarg.s  0xD
0xd89d  ldarg.s  0xE
0xd89f  call     instance unsigned int8[] Microsoft.Crm.WebServices.ExportXmlService::ExportSolutionWithTargetVersion(string solutionName, bool managed, string targetVersion, bool exportAutoNumberingSettings, bool exportCalendarSettings, bool exportCustomizationSettings, bool exportEmailTrackingSettings, bool exportGeneralSettings, bool exportMarketingSettings, bool exportOutlookSynchronizationSettings, bool exportRelationshipRoles, bool exportIsvConfig, bool exportSales, bool exportExternalApplications, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd8a4  ret
```
