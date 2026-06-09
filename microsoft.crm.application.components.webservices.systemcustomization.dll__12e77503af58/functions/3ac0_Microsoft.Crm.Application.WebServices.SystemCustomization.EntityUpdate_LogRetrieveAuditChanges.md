# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::LogRetrieveAuditChanges

- ea: `0x3ac0`
- end: `0x3c09`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::LogRetrieveAuditChanges`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x2b0`
- `0x3ac0`

## string_xrefs

- `0x3beb`: `UpdateAuditSettings`

## pseudocode

```c

```

## disassembly

```asm
0x3ac0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::.ctor()
0x3ac5  stloc.0
0x3ac6  ldarg.1
0x3ac7  ldstr    aAuditenabled// "auditenabled"
0x3acc  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3ad1  brfalse.s loc_3B0B
0x3ad3  ldarg.1
0x3ad4  ldstr    aAuditenabled// "auditenabled"
0x3ad9  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3ade  stloc.1
0x3adf  ldarg.0
0x3ae0  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsAuditEnabled()
0x3ae5  ldloc.1
0x3ae6  beq.s    loc_3B0B
0x3ae8  ldloc.0
0x3ae9  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::.ctor()
0x3aee  dup
0x3aef  ldstr    aIsauditenabled// "IsAuditEnabled"
0x3af4  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Key(string)
0x3af9  dup
0x3afa  ldloca.s 1
0x3afc  call     instance string [mscorlib]System.Boolean::ToString()
0x3b01  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Value(string)
0x3b06  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::Add(var<u1>)
0x3b0b  ldarg.1
0x3b0c  ldstr    aRetrieveaudite// "retrieveauditenabled"
0x3b11  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3b16  brfalse.s loc_3B50
0x3b18  ldarg.1
0x3b19  ldstr    aRetrieveaudite// "retrieveauditenabled"
0x3b1e  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3b23  stloc.2
0x3b24  ldarg.0
0x3b25  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsRetrieveAuditEnabled()
0x3b2a  ldloc.2
0x3b2b  beq.s    loc_3B50
0x3b2d  ldloc.0
0x3b2e  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::.ctor()
0x3b33  dup
0x3b34  ldstr    aIsretrieveaudi// "IsRetrieveAuditEnabled"
0x3b39  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Key(string)
0x3b3e  dup
0x3b3f  ldloca.s 2
0x3b41  call     instance string [mscorlib]System.Boolean::ToString()
0x3b46  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Value(string)
0x3b4b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::Add(var<u1>)
0x3b50  ldarg.1
0x3b51  ldstr    aRetrievemultip// "retrievemultipleauditenabled"
0x3b56  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3b5b  brfalse.s loc_3B95
0x3b5d  ldarg.1
0x3b5e  ldstr    aRetrievemultip// "retrievemultipleauditenabled"
0x3b63  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3b68  stloc.3
0x3b69  ldarg.0
0x3b6a  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsRetrieveMultipleAuditEnabled()
0x3b6f  ldloc.3
0x3b70  beq.s    loc_3B95
0x3b72  ldloc.0
0x3b73  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::.ctor()
0x3b78  dup
0x3b79  ldstr    aIsretrievemult// "IsRetrieveMultipleAuditEnabled"
0x3b7e  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Key(string)
0x3b83  dup
0x3b84  ldloca.s 3
0x3b86  call     instance string [mscorlib]System.Boolean::ToString()
0x3b8b  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData::set_Value(string)
0x3b90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::Add(var<u1>)
0x3b95  ldloc.0
0x3b96  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>::get_Count()
0x3b9b  ldc.i4.0
0x3b9c  ble.s    loc_3C08
0x3b9e  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::.ctor()
0x3ba3  stloc.s  4
0x3ba5  ldloc.s  4
0x3ba7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3bac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x3bb1  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_SystemUserId(valuetype [mscorlib]System.Guid)
0x3bb6  ldloc.s  4
0x3bb8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3bbd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x3bc2  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x3bc7  ldloc.s  4
0x3bc9  ldloc.0
0x3bca  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_Fields(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.KeyValueData>)
0x3bcf  ldloc.s  4
0x3bd1  ldarg.0
0x3bd2  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_LogicalName()
0x3bd7  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_EntityName(string)
0x3bdc  ldloc.s  4
0x3bde  ldarg.0
0x3bdf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x3be4  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_EntityId(valuetype [mscorlib]System.Guid)
0x3be9  ldloc.s  4
0x3beb  ldstr    aUpdateauditset// "UpdateAuditSettings"
0x3bf0  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::set_Operation(string)
0x3bf5  ldloc.s  4
0x3bf7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData::get_OrganizationId()
0x3bfc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x3c01  ldloc.s  4
0x3c03  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLogging::LogRequest(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLoggingData)
0x3c08  ret
```
