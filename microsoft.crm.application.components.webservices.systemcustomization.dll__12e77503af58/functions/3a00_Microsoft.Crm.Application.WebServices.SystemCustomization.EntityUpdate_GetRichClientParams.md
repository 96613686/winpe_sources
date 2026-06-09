# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetRichClientParams

- ea: `0x3a00`
- end: `0x3a38`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetRichClientParams`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x1a0`
- `0x2b0`
- `0x3a00`

## pseudocode

```c

```

## disassembly

```asm
0x3a00  ldarg.1
0x3a01  ldstr    aRichclient// "richclient"
0x3a06  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3a0b  brfalse.s loc_3A37
0x3a0d  ldarg.1
0x3a0e  ldstr    aRichclient// "richclient"
0x3a13  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x3a18  stloc.0
0x3a19  ldloc.0
0x3a1a  ldstr    aOffline// "offline"
0x3a1f  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3a24  brfalse.s loc_3A37
0x3a26  ldarg.0
0x3a27  ldloc.0
0x3a28  ldstr    aOffline// "offline"
0x3a2d  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3a32  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_AvailableOffline(bool)
0x3a37  ret
```
