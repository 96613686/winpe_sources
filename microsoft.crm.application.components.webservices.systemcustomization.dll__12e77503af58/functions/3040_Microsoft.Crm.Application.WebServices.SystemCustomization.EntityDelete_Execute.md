# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityDelete::Execute

- ea: `0x3040`
- end: `0x309b`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityDelete::Execute`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xb0b0`

## callees

- `0x3040`
- `0x30a0`
- `0x3100`

## pseudocode

```c

```

## disassembly

```asm
0x3040  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteEntity()
0x3045  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x304a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x304f  brtrue.s loc_3062
0x3051  ldc.i4   0x80040277
0x3056  ldc.i4.0
0x3057  newarr   [mscorlib]System.Object
0x305c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3061  throw
0x3062  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityService::.ctor()
0x3067  ldarg.1
0x3068  call     string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityDelete::GetEntityLogicalName(valuetype [mscorlib]System.Guid entityId)
0x306d  stloc.0
0x306e  ldarg.1
0x306f  ldarg.0
0x3070  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3075  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x307a  brtrue.s loc_307F
0x307c  ldarg.0
0x307d  br.s     loc_3084
0x307f  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x3084  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityService::Delete(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3089  ldarg.1
0x308a  ldloc.0
0x308b  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityDelete::LogDeleteEntity(valuetype [mscorlib]System.Guid entityId, string entityLogicalName)
0x3090  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3095  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x309a  ret
```
