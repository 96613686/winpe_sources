# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityKeyCreate::Execute

- ea: `0x3140`
- end: `0x31a1`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityKeyCreate::Execute`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xbac0`

## callees

- `0x330`
- `0x3140`
- `0x31b0`

## pseudocode

```c

```

## disassembly

```asm
0x3140  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateEntityKey()
0x3145  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x314a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x314f  brtrue.s loc_3162
0x3151  ldc.i4   0x80040277
0x3156  ldc.i4.0
0x3157  newarr   [mscorlib]System.Object
0x315c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3161  throw
0x3162  ldarg.1
0x3163  ldstr    aEntityid// "entityid"
0x3168  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x316d  stloc.0
0x316e  ldarg.1
0x316f  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo Microsoft.Crm.Application.WebServices.SystemCustomization.EntityKeyCreate::GetEntityKeyInfo(class Microsoft.Crm.Application.WebServices.ParameterBag parameterBag)
0x3174  stloc.1
0x3175  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyService::.ctor()
0x317a  ldloc.0
0x317b  ldloc.1
0x317c  ldarg.0
0x317d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3182  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3187  brtrue.s loc_318C
0x3189  ldarg.0
0x318a  br.s     loc_3191
0x318c  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x3191  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyService::Create(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityKeyCreateInfo, valuetype [mscorlib]System.Guid)
0x3196  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x319b  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x31a0  ret
```
