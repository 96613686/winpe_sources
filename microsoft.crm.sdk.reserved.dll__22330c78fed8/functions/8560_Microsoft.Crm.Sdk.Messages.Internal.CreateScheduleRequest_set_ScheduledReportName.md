# Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::set_ScheduledReportName

- ea: `0x8560`
- end: `0x8572`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::set_ScheduledReportName`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x8580`

## string_xrefs

- `0x8566`: `ScheduledReportName`

## pseudocode

```c

```

## disassembly

```asm
0x8560  ldarg.0
0x8561  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8566  ldstr    aScheduledrepor// "ScheduledReportName"
0x856b  ldarg.1
0x856c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8571  ret
```
