# Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::VerifyRoleAccessPrivileges

- ea: `0x5fb80`
- end: `0x5fc07`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::VerifyRoleAccessPrivileges`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x5f250`

## callees

- `0x357b0`
- `0x5fb80`

## string_xrefs

- `0x5fba4`: `prvReadRole`
- `0x5fbc0`: `prvWriteRole`
- `0x5fbdc`: `prvCreateRole`

## pseudocode

```c

```

## disassembly

```asm
0x5fb80  ldarg.0
0x5fb81  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fb86  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x5fb8b  stloc.0
0x5fb8c  ldarg.0
0x5fb8d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fb92  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5fb97  ldstr    aRole// "Role"
0x5fb9c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x5fba1  stloc.1
0x5fba2  ldloc.0
0x5fba3  ldloc.1
0x5fba4  ldstr    aPrvreadrole// "prvReadRole"
0x5fba9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(string)
0x5fbae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x5fbb3  ldarg.0
0x5fbb4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fbb9  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5fbbe  ldloc.0
0x5fbbf  ldloc.1
0x5fbc0  ldstr    aPrvwriterole// "prvWriteRole"
0x5fbc5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(string)
0x5fbca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x5fbcf  ldarg.0
0x5fbd0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fbd5  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5fbda  ldloc.0
0x5fbdb  ldloc.1
0x5fbdc  ldstr    aPrvcreaterole// "prvCreateRole"
0x5fbe1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(string)
0x5fbe6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x5fbeb  ldarg.0
0x5fbec  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fbf1  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5fbf6  leave.s  loc_5FC06
0x5fbf8  stloc.2
0x5fbf9  ldloc.2
0x5fbfa  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5fbff  ldloc.2
0x5fc00  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportRolePermissionException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x5fc05  throw
0x5fc06  ret
```
