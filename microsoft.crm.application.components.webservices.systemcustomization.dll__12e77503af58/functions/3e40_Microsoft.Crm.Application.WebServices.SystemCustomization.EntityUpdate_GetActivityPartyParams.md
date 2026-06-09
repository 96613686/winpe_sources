# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetActivityPartyParams

- ea: `0x3e40`
- end: `0x3eaa`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetActivityPartyParams`
- size: `106`
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
- `0x3e40`

## pseudocode

```c

```

## disassembly

```asm
0x3e40  ldarg.2
0x3e41  ldstr    aAssociatedenti// "associatedentity"
0x3e46  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3e4b  brfalse.s loc_3EA9
0x3e4d  ldarg.1
0x3e4e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0x3e53  brfalse.s loc_3EA9
0x3e55  ldarg.1
0x3e56  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x3e5b  brtrue.s loc_3EA9
0x3e5d  ldarg.1
0x3e5e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivityParty()
0x3e63  brtrue.s loc_3EA9
0x3e65  ldarg.1
0x3e66  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x3e6b  brtrue.s loc_3E7F
0x3e6d  ldsfld   class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::activityPartyRelationshipAllowList
0x3e72  ldarg.1
0x3e73  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x3e78  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<int32>::Contains(var<u1>)
0x3e7d  brfalse.s loc_3EA9
0x3e7f  ldarg.2
0x3e80  ldstr    aAssociatedenti// "associatedentity"
0x3e85  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x3e8a  stloc.0
0x3e8b  ldloc.0
0x3e8c  ldstr    aActivitypartie// "activityparties"
0x3e91  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3e96  brfalse.s loc_3EA9
0x3e98  ldarg.0
0x3e99  ldloc.0
0x3e9a  ldstr    aActivitypartie// "activityparties"
0x3e9f  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3ea4  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsActivityParty(bool)
0x3ea9  ret
```
