# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetOneNoteIntegrationParams

- ea: `0x3da0`
- end: `0x3dc0`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetOneNoteIntegrationParams`
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
- `0x3da0`

## pseudocode

```c

```

## disassembly

```asm
0x3da0  ldarg.1
0x3da1  ldstr    aOnenoteintegra// "onenoteintegrationenabled"
0x3da6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3dab  brfalse.s loc_3DBF
0x3dad  ldarg.0
0x3dae  ldarg.1
0x3daf  ldstr    aOnenoteintegra// "onenoteintegrationenabled"
0x3db4  ldc.i4.0
0x3db5  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x3dba  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsOneNoteIntegrationEnabled(bool)
0x3dbf  ret
```
