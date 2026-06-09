# Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::HasRelationshipRolePrivilege

- ea: `0x570f0`
- end: `0x571d1`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::HasRelationshipRolePrivilege`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x57200`

## callees

- `0x570f0`

## string_xrefs

- `0x5710c`: `prvCreateRelationshipRole`
- `0x5712c`: `prvWriteRelationshipRole`
- `0x5714c`: `prvReadRelationshipRole`

## pseudocode

```c

```

## disassembly

```asm
0x570f0  ldarg.1
0x570f1  ldsfld   string [mscorlib]System.String::Empty
0x570f6  stind.ref
0x570f7  ldarg.0
0x570f8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::context
0x570fd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x57102  ldstr    aRelationshipro_1// "RelationshipRole"
0x57107  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x5710c  ldstr    aPrvcreaterelat// "prvCreateRelationshipRole"
0x57111  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(string)
0x57116  stloc.0
0x57117  ldarg.0
0x57118  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::context
0x5711d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x57122  ldstr    aRelationshipro_1// "RelationshipRole"
0x57127  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x5712c  ldstr    aPrvwriterelati// "prvWriteRelationshipRole"
0x57131  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(string)
0x57136  stloc.1
0x57137  ldarg.0
0x57138  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::context
0x5713d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x57142  ldstr    aRelationshipro_1// "RelationshipRole"
0x57147  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x5714c  ldstr    aPrvreadrelatio// "prvReadRelationshipRole"
0x57151  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(string)
0x57156  stloc.2
0x57157  ldarg.0
0x57158  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::context
0x5715d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x57162  ldloc.0
0x57163  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x57168  ldarg.0
0x57169  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::context
0x5716e  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x57173  brfalse.s loc_5717F
0x57175  ldarg.1
0x57176  ldloc.0
0x57177  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Name()
0x5717c  stind.ref
0x5717d  ldc.i4.0
0x5717e  ret
0x5717f  ldarg.0
0x57180  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::context
0x57185  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x5718a  ldloc.1
0x5718b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x57190  ldarg.0
0x57191  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::context
0x57196  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5719b  brfalse.s loc_571A7
0x5719d  ldarg.1
0x5719e  ldloc.1
0x5719f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Name()
0x571a4  stind.ref
0x571a5  ldc.i4.0
0x571a6  ret
0x571a7  ldarg.0
0x571a8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::context
0x571ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x571b2  ldloc.2
0x571b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x571b8  ldarg.0
0x571b9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRelationshipRoleHandler::context
0x571be  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x571c3  brfalse.s loc_571CF
0x571c5  ldarg.1
0x571c6  ldloc.2
0x571c7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Name()
0x571cc  stind.ref
0x571cd  ldc.i4.0
0x571ce  ret
0x571cf  ldc.i4.1
0x571d0  ret
```
