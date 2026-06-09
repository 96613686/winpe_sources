# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetChangeTrackingParams

- ea: `0x3c90`
- end: `0x3cb0`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetChangeTrackingParams`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x290`
- `0x3c90`

## pseudocode

```c

```

## disassembly

```asm
0x3c90  ldarg.1
0x3c91  ldstr    aChangetracking// "changetrackingenabled"
0x3c96  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3c9b  brfalse.s loc_3CAF
0x3c9d  ldarg.0
0x3c9e  ldarg.1
0x3c9f  ldstr    aChangetracking// "changetrackingenabled"
0x3ca4  ldc.i4.0
0x3ca5  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x3caa  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_ChangeTrackingEnabled(bool)
0x3caf  ret
```
