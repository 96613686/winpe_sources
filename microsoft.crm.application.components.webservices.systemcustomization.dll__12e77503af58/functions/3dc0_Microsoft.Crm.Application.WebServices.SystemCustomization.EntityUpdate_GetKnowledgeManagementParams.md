# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetKnowledgeManagementParams

- ea: `0x3dc0`
- end: `0x3de0`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetKnowledgeManagementParams`
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
- `0x3dc0`

## pseudocode

```c

```

## disassembly

```asm
0x3dc0  ldarg.1
0x3dc1  ldstr    aKnowledgemgmte// "knowledgemgmtenabled"
0x3dc6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3dcb  brfalse.s loc_3DDF
0x3dcd  ldarg.0
0x3dce  ldarg.1
0x3dcf  ldstr    aKnowledgemgmte// "knowledgemgmtenabled"
0x3dd4  ldc.i4.0
0x3dd5  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x3dda  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsKnowledgeManagementEnabled(bool)
0x3ddf  ret
```
