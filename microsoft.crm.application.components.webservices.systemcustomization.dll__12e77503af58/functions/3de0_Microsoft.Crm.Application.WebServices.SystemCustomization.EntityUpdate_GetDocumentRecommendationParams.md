# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetDocumentRecommendationParams

- ea: `0x3de0`
- end: `0x3e00`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetDocumentRecommendationParams`
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
- `0x3de0`

## string_xrefs

- `0x3de1`: `documentrecommendationsenabled`
- `0x3def`: `documentrecommendationsenabled`

## pseudocode

```c

```

## disassembly

```asm
0x3de0  ldarg.1
0x3de1  ldstr    aDocumentrecomm// "documentrecommendationsenabled"
0x3de6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3deb  brfalse.s loc_3DFF
0x3ded  ldarg.0
0x3dee  ldarg.1
0x3def  ldstr    aDocumentrecomm// "documentrecommendationsenabled"
0x3df4  ldc.i4.0
0x3df5  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x3dfa  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsDocumentRecommendationsEnabled(bool)
0x3dff  ret
```
