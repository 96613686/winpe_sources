# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetBusinessProcessParams

- ea: `0x3ff0`
- end: `0x401f`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetBusinessProcessParams`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x2b0`
- `0x3ff0`

## pseudocode

```c

```

## disassembly

```asm
0x3ff0  ldarg.1
0x3ff1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBusinessProcessEnabled()
0x3ff6  brtrue.s loc_401E
0x3ff8  ldarg.1
0x3ff9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x3ffe  brfalse.s loc_401E
0x4000  ldarg.2
0x4001  ldstr    aBusinessproces// "businessprocessenabled"
0x4006  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x400b  brfalse.s loc_401E
0x400d  ldarg.0
0x400e  ldarg.2
0x400f  ldstr    aBusinessproces// "businessprocessenabled"
0x4014  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x4019  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsBusinessProcessEnabled(bool)
0x401e  ret
```
