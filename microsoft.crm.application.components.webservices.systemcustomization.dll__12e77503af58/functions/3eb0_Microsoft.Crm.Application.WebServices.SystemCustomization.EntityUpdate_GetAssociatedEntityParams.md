# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAssociatedEntityParams

- ea: `0x3eb0`
- end: `0x3f1e`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAssociatedEntityParams`
- size: `110`
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
- `0x3eb0`

## pseudocode

```c

```

## disassembly

```asm
0x3eb0  ldarg.1
0x3eb1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x3eb6  brfalse.s loc_3F1D
0x3eb8  ldarg.2
0x3eb9  ldstr    aAssociatedenti// "associatedentity"
0x3ebe  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3ec3  brfalse.s loc_3F1D
0x3ec5  ldarg.2
0x3ec6  ldstr    aAssociatedenti// "associatedentity"
0x3ecb  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x3ed0  stloc.0
0x3ed1  ldarg.0
0x3ed2  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedNotes()
0x3ed7  brtrue.s loc_3EF7
0x3ed9  ldloc.0
0x3eda  ldstr    aNotes// "notes"
0x3edf  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3ee4  brfalse.s loc_3EF7
0x3ee6  ldarg.0
0x3ee7  ldloc.0
0x3ee8  ldstr    aNotes// "notes"
0x3eed  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3ef2  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_HasRelatedNotes(bool)
0x3ef7  ldarg.0
0x3ef8  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedActivities()
0x3efd  brtrue.s loc_3F1D
0x3eff  ldloc.0
0x3f00  ldstr    aActivities// "activities"
0x3f05  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3f0a  brfalse.s loc_3F1D
0x3f0c  ldarg.0
0x3f0d  ldloc.0
0x3f0e  ldstr    aActivities// "activities"
0x3f13  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3f18  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_HasRelatedActivities(bool)
0x3f1d  ret
```
