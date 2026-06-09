# Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::get_UnchangedTimeField

- ea: `0x6ee00`
- end: `0x6ee2e`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::get_UnchangedTimeField`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5f990`

## callees

- `0x6ee00`

## string_xrefs

- `0x6ee10`: `scheduledstart`
- `0x6ee26`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x6ee00  ldarg.0
0x6ee01  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::_scheduledEndChanged
0x6ee06  brfalse.s loc_6EE16
0x6ee08  ldarg.0
0x6ee09  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::_scheduledStartChanged
0x6ee0e  brtrue.s loc_6EE16
0x6ee10  ldstr    aScheduledstart// "scheduledstart"
0x6ee15  ret
0x6ee16  ldarg.0
0x6ee17  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::_scheduledStartChanged
0x6ee1c  brfalse.s loc_6EE2C
0x6ee1e  ldarg.0
0x6ee1f  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForAppointment::_scheduledEndChanged
0x6ee24  brtrue.s loc_6EE2C
0x6ee26  ldstr    aScheduledend// "scheduledend"
0x6ee2b  ret
0x6ee2c  ldnull
0x6ee2d  ret
```
