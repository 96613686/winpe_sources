# Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::Collect

- ea: `0x4990`
- end: `0x49ea`
- name: `Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::Collect`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x4310`
- `0x4990`
- `0x49f0`
- `0x4f70`

## pseudocode

```c

```

## disassembly

```asm
0x4990  ldarg.0
0x4991  call     instance class Microsoft.Crm.Asynchronous.PlatformCollectorHelper Microsoft.Crm.Asynchronous.SqmCollectorBase::get_PlatformCollectorHelper()
0x4996  ldc.i4   0x1076
0x499b  ldarg.0
0x499c  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::_configuration
0x49a1  callvirt instance int32 Microsoft.Crm.Asynchronous.PlatformCollectorHelper::GetEntityCount(int32 objectTypeCode, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x49a6  stloc.0
0x49a7  ldarg.1
0x49a8  ldc.i4.s 0x7B
0x49aa  ldloc.0
0x49ab  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x49b0  ldloc.0
0x49b1  ldc.i4.0
0x49b2  ble.s    loc_49E9
0x49b4  ldarg.0
0x49b5  ldc.i4   0xFA0
0x49ba  call     instance int32 Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::GetTotalResourceParticipantCount(int32 partyObjectTypeCode)
0x49bf  stloc.1
0x49c0  ldarg.1
0x49c1  ldc.i4.s 0x7C
0x49c3  ldloc.1
0x49c4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x49c9  ldarg.0
0x49ca  ldc.i4.8
0x49cb  call     instance int32 Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::GetTotalResourceParticipantCount(int32 partyObjectTypeCode)
0x49d0  stloc.2
0x49d1  ldarg.1
0x49d2  ldc.i4.s 0x7D
0x49d4  ldloc.2
0x49d5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x49da  ldloc.1
0x49db  ldloc.2
0x49dc  add
0x49dd  stloc.3
0x49de  ldarg.1
0x49df  ldc.i4.s 0x76
0x49e1  ldloc.3
0x49e2  ldloc.0
0x49e3  div
0x49e4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x49e9  ret
```
