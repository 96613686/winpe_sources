# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetQuickCreateParams

- ea: `0x4100`
- end: `0x411f`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetQuickCreateParams`
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
- `0x4100`

## string_xrefs

- `0x4101`: `isquickcreateenabled`
- `0x410f`: `isquickcreateenabled`

## pseudocode

```c

```

## disassembly

```asm
0x4100  ldarg.1
0x4101  ldstr    aIsquickcreatee// "isquickcreateenabled"
0x4106  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x410b  brfalse.s loc_411E
0x410d  ldarg.0
0x410e  ldarg.1
0x410f  ldstr    aIsquickcreatee// "isquickcreateenabled"
0x4114  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x4119  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsQuickCreateEnabled(bool)
0x411e  ret
```
