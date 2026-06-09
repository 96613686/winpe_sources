# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetDocumentManagementParams

- ea: `0x3cb0`
- end: `0x3ccf`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetDocumentManagementParams`
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
- `0x3cb0`

## pseudocode

```c

```

## disassembly

```asm
0x3cb0  ldarg.1
0x3cb1  ldstr    aDocmgmtenabled// "docmgmtenabled"
0x3cb6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3cbb  brfalse.s loc_3CCE
0x3cbd  ldarg.0
0x3cbe  ldarg.1
0x3cbf  ldstr    aDocmgmtenabled// "docmgmtenabled"
0x3cc4  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3cc9  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsDocumentManagementEnabled(bool)
0x3cce  ret
```
