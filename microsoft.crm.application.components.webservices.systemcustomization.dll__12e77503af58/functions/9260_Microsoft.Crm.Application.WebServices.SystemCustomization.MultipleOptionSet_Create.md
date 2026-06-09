# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::Create

- ea: `0x9260`
- end: `0x92a0`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::Create`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xb0f0`

## callees

- `0x9260`
- `0x9a10`

## pseudocode

```c

```

## disassembly

```asm
0x9260  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateOptionSet()
0x9265  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x926a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x926f  brtrue.s loc_9282
0x9271  ldc.i4   0x80040277
0x9276  ldc.i4.0
0x9277  newarr   [mscorlib]System.Object
0x927c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x9281  throw
0x9282  ldarg.1
0x9283  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetCreateInfo Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetCreateInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x9288  stloc.0
0x9289  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetService::.ctor()
0x928e  ldloc.0
0x928f  ldarg.0
0x9290  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetService::Create(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetCreateInfo, valuetype [mscorlib]System.Guid)
0x9295  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x929a  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x929f  ret
```
