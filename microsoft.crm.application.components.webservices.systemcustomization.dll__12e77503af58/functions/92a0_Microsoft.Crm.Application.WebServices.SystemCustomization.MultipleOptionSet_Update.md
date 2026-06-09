# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::Update

- ea: `0x92a0`
- end: `0x92ec`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::Update`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xb130`

## callees

- `0x92a0`
- `0x9bd0`

## pseudocode

```c

```

## disassembly

```asm
0x92a0  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteOptionSet()
0x92a5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x92aa  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x92af  brtrue.s loc_92C2
0x92b1  ldc.i4   0x80040277
0x92b6  ldc.i4.0
0x92b7  newarr   [mscorlib]System.Object
0x92bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x92c1  throw
0x92c2  ldarg.1
0x92c3  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetUpdateInfo Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetUpdateInfo(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x92c8  stloc.0
0x92c9  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetService::.ctor()
0x92ce  ldloc.0
0x92cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x92d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x92d9  ldloc.0
0x92da  ldc.i4.1
0x92db  ldarg.0
0x92dc  call     instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetService::Update(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetUpdateInfo, bool, valuetype [mscorlib]System.Guid)
0x92e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x92e6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x92eb  ret
```
