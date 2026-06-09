# Microsoft.Crm.Sdk.Messages.Internal.DeleteCalendarRequest::.ctor

- ea: `0x1e90`
- end: `0x1eb7`
- name: `Microsoft.Crm.Sdk.Messages.Internal.DeleteCalendarRequest::.ctor`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1dd0`
- `0x1e20`
- `0x1e70`

## string_xrefs

- `0x1e97`: `DeleteCalendar`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  ldarg.0
0x1e91  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x1e96  ldarg.0
0x1e97  ldstr    aDeletecalendar// "DeleteCalendar"
0x1e9c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x1ea1  ldarg.0
0x1ea2  ldnull
0x1ea3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.DeleteCalendarRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x1ea8  ldarg.0
0x1ea9  ldc.i4.0
0x1eaa  call     instance void Microsoft.Crm.Sdk.Messages.Internal.DeleteCalendarRequest::set_SkipSharedCalendar(bool value)
0x1eaf  ldarg.0
0x1eb0  ldc.i4.0
0x1eb1  call     instance void Microsoft.Crm.Sdk.Messages.Internal.DeleteCalendarRequest::set_SkipChildCalendar(bool value)
0x1eb6  ret
```
