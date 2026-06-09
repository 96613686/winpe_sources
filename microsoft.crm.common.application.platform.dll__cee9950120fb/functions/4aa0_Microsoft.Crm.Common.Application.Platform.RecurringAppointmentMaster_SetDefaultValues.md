# Microsoft.Crm.Common.Application.Platform.RecurringAppointmentMaster::SetDefaultValues

- ea: `0x4aa0`
- end: `0x4abf`
- name: `Microsoft.Crm.Common.Application.Platform.RecurringAppointmentMaster::SetDefaultValues`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2850`
- `0x4aa0`

## pseudocode

```c

```

## disassembly

```asm
0x4aa0  ldarg.0
0x4aa1  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::SetDefaultValues()
0x4aa6  ldarg.0
0x4aa7  ldstr    aOrganizer// "organizer"
0x4aac  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x4ab1  brtrue.s loc_4ABE
0x4ab3  ldarg.0
0x4ab4  ldstr    aOrganizer// "organizer"
0x4ab9  callvirt instance void Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulatePartyToCurrentUser(string participationTypeName)
0x4abe  ret
```
