# Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::get_ScheduledReportName

- ea: `0x8530`
- end: `0x855a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateScheduleRequest::get_ScheduledReportName`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8530`

## string_xrefs

- `0x8536`: `ScheduledReportName`
- `0x8548`: `ScheduledReportName`

## pseudocode

```c

```

## disassembly

```asm
0x8530  ldarg.0
0x8531  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8536  ldstr    aScheduledrepor// "ScheduledReportName"
0x853b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x8540  brfalse.s loc_8558
0x8542  ldarg.0
0x8543  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8548  ldstr    aScheduledrepor// "ScheduledReportName"
0x854d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8552  castclass [mscorlib]System.String
0x8557  ret
0x8558  ldnull
0x8559  ret
```
