# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetConnectionsParams

- ea: `0x3f80`
- end: `0x3fe6`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetConnectionsParams`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x2b0`
- `0x3f80`

## pseudocode

```c

```

## disassembly

```asm
0x3f80  ldarg.1
0x3f81  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsConnectionsEnabled()
0x3f86  brtrue.s loc_3FE5
0x3f88  ldarg.2
0x3f89  ldstr    aConnection// "connection"
0x3f8e  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3f93  brfalse.s loc_3FE5
0x3f95  ldarg.1
0x3f96  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x3f9b  ldc.i4   0xCA2
0x3fa0  beq.s    loc_3FCC
0x3fa2  ldarg.1
0x3fa3  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x3fa8  ldc.i4   0xC9F
0x3fad  beq.s    loc_3FCC
0x3faf  ldarg.1
0x3fb0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x3fb5  brfalse.s loc_3FCC
0x3fb7  ldarg.1
0x3fb8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x3fbd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsLogical()
0x3fc2  brtrue.s loc_3FCC
0x3fc4  ldarg.1
0x3fc5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0x3fca  brtrue.s loc_3FD4
0x3fcc  ldarg.0
0x3fcd  ldc.i4.0
0x3fce  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsConnectionsEnabled(bool)
0x3fd3  ret
0x3fd4  ldarg.0
0x3fd5  ldarg.2
0x3fd6  ldstr    aConnection// "connection"
0x3fdb  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3fe0  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsConnectionsEnabled(bool)
0x3fe5  ret
```
