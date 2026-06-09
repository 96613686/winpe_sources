# Microsoft.Crm.Sdk.Messages.Internal.UpdateScheduleRequest::get_ScheduledReportName

- ea: `0x8730`
- end: `0x875a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateScheduleRequest::get_ScheduledReportName`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x8730`

## string_xrefs

- `0x8736`: `ScheduledReportName`
- `0x8748`: `ScheduledReportName`

## pseudocode

```c

```

## disassembly

```asm
0x8730  ldarg.0
0x8731  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8736  ldstr    aScheduledrepor// "ScheduledReportName"
0x873b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x8740  brfalse.s loc_8758
0x8742  ldarg.0
0x8743  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8748  ldstr    aScheduledrepor// "ScheduledReportName"
0x874d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8752  castclass [mscorlib]System.String
0x8757  ret
0x8758  ldnull
0x8759  ret
```
