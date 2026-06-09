# Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::GetSubAreaType

- ea: `0x13ed0`
- end: `0x13f30`
- name: `Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::GetSubAreaType`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x135a0`

## callees

- `0x13ed0`

## string_xrefs

- `0x13ede`: `serviceappointment`

## pseudocode

```c

```

## disassembly

```asm
0x13ed0  ldarg.1
0x13ed1  ldstr    aActivitypointe// "activitypointer"
0x13ed6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13edb  brtrue.s loc_13F20
0x13edd  ldarg.1
0x13ede  ldstr    aServiceappoint// "serviceappointment"
0x13ee3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13ee8  brtrue.s loc_13F20
0x13eea  ldarg.1
0x13eeb  ldstr    aAppointment// "appointment"
0x13ef0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13ef5  brtrue.s loc_13F20
0x13ef7  ldarg.1
0x13ef8  ldstr    aResource// "resource"
0x13efd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13f02  brtrue.s loc_13F28
0x13f04  ldarg.1
0x13f05  ldstr    aSystemuser// "systemuser"
0x13f0a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13f0f  brtrue.s loc_13F28
0x13f11  ldarg.1
0x13f12  ldstr    aEquipment// "equipment"
0x13f17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13f1c  brtrue.s loc_13F28
0x13f1e  br.s     loc_13F28
0x13f20  ldstr    aApptbook// "apptbook"
0x13f25  stloc.0
0x13f26  br.s     loc_13F2E
0x13f28  ldstr    aSchedules// "schedules"
0x13f2d  stloc.0
0x13f2e  ldloc.0
0x13f2f  ret
```
