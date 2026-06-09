# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdateEnforceStateTransitions

- ea: `0x3880`
- end: `0x3920`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdateEnforceStateTransitions`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xb930`

## callees

- `0x190`
- `0x2b0`
- `0x330`
- `0x3880`
- `0x4120`

## pseudocode

```c

```

## disassembly

```asm
0x3880  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::CheckPrivileges()
0x3885  ldarg.1
0x3886  ldstr    aEntityid// "entityid"
0x388b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x3890  stloc.0
0x3891  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3896  stloc.1
0x3897  ldloc.1
0x3898  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x389d  ldloc.0
0x389e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x38a3  stloc.2
0x38a4  ldloc.2
0x38a5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0x38aa  brfalse.s loc_391F
0x38ac  ldloc.2
0x38ad  ldloc.1
0x38ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x38b3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::IsStateModelAware(valuetype [mscorlib]System.Guid)
0x38b8  brfalse.s loc_391F
0x38ba  ldloc.0
0x38bb  ldloc.1
0x38bc  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x38c1  stloc.3
0x38c2  ldarg.1
0x38c3  ldstr    aEnforcestatetr// "enforcestatetransitions"
0x38c8  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x38cd  brfalse.s loc_38E0
0x38cf  ldloc.3
0x38d0  ldarg.1
0x38d1  ldstr    aEnforcestatetr// "enforcestatetransitions"
0x38d6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x38db  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_EnforceStateTransitions(bool)
0x38e0  ldloc.3
0x38e1  ldloc.2
0x38e2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsAuditEnabled()
0x38e7  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsAuditEnabled(bool)
0x38ec  ldloc.2
0x38ed  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityService [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityServiceFactory::CreateEntityService(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x38f2  ldloc.0
0x38f3  ldloc.3
0x38f4  ldc.i4.0
0x38f5  ldarg.0
0x38f6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38fb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3900  brtrue.s loc_3905
0x3902  ldarg.0
0x3903  br.s     loc_390A
0x3905  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x390a  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityService::Update(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo, bool, valuetype [mscorlib]System.Guid)
0x390f  ldloc.2
0x3910  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x3915  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x391a  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x391f  ret
```
