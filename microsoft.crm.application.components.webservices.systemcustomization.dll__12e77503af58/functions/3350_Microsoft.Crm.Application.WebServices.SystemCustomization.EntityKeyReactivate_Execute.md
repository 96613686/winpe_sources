# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityKeyReactivate::Execute

- ea: `0x3350`
- end: `0x339d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityKeyReactivate::Execute`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbaf0`

## callees

- `0x3350`

## pseudocode

```c

```

## disassembly

```asm
0x3350  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateEntityKey()
0x3355  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x335a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x335f  brtrue.s loc_3372
0x3361  ldc.i4   0x80040277
0x3366  ldc.i4.0
0x3367  newarr   [mscorlib]System.Object
0x336c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3371  throw
0x3372  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyService::.ctor()
0x3377  ldarg.0
0x3378  ldarg.1
0x3379  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x337e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3383  brtrue.s loc_3388
0x3385  ldarg.1
0x3386  br.s     loc_338D
0x3388  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x338d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyService::ReactivateEntityKey(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3392  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3397  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x339c  ret
```
