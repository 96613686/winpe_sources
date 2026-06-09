# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetDuplicateDetectionParams

- ea: `0x3a60`
- end: `0x3a7f`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetDuplicateDetectionParams`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x2b0`
- `0x3a60`

## pseudocode

```c

```

## disassembly

```asm
0x3a60  ldarg.1
0x3a61  ldstr    aDuplicatecheck// "duplicatecheck"
0x3a66  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3a6b  brfalse.s loc_3A7E
0x3a6d  ldarg.0
0x3a6e  ldarg.1
0x3a6f  ldstr    aDuplicatecheck// "duplicatecheck"
0x3a74  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3a79  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsDuplicateCheckSupported(bool)
0x3a7e  ret
```
