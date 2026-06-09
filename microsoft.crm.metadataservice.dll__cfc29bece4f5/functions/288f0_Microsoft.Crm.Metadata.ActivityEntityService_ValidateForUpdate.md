# Microsoft.Crm.Metadata.ActivityEntityService::ValidateForUpdate

- ea: `0x288f0`
- end: `0x28a4d`
- name: `Microsoft.Crm.Metadata.ActivityEntityService::ValidateForUpdate`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x288f0`
- `0x28a50`
- `0x39620`
- `0x3cb50`
- `0x3cc80`
- `0x3cca0`
- `0x3d180`
- `0x3d1a0`
- `0x3d7b0`

## string_xrefs

- `0x289b5`: `A custom entity defined as an activity already cannot have MailMerge enabled.`
- `0x2893a`: `A custom entity defined as an communication activity type can not be reverted back to normal type.`

## pseudocode

```c

```

## disassembly

```asm
0x288f0  ldarg.0
0x288f1  ldarg.1
0x288f2  ldarg.2
0x288f3  ldarg.3
0x288f4  ldarg.s  4
0x288f6  ldarg.s  5
0x288f8  ldarg.s  6
0x288fa  ldarg.s  7
0x288fc  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateForUpdate(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity primaryFieldAttribute, bool isInternalSolutionContext, bool isExistingEntityManaged, bool mergeLabels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x28901  ldarg.1
0x28902  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x28907  ldstr    aIsactivity// "isactivity"
0x2890c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x28911  brfalse.s loc_28930
0x28913  ldarg.1
0x28914  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x28919  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsActivity()
0x2891e  brtrue.s loc_28930
0x28920  ldstr    aACustomEntityD_3// "A custom entity defined as an activity "...
0x28925  ldc.i4   0x8004F126
0x2892a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2892f  throw
0x28930  ldarg.0
0x28931  ldarg.1
0x28932  ldarg.2
0x28933  call     instance bool Microsoft.Crm.Metadata.ActivityEntityService::IsCommunicationActivityPropertyModified(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x28938  brfalse.s loc_2894A
0x2893a  ldstr    aACustomEntityD_4// "A custom entity defined as an communica"...
0x2893f  ldc.i4   0x8004F126
0x28944  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x28949  throw
0x2894a  ldarg.1
0x2894b  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedActivities()
0x28950  brfalse.s loc_28990
0x28952  ldarg.1
0x28953  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x28958  ldstr    a87e909a7E37840// "87e909a7-e378-407e-92f2-2dab2a6b7ca6"
0x2895d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x28962  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28967  brfalse.s loc_28990
0x28969  ldarg.1
0x2896a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x2896f  ldstr    aB237ecf9E36141// "b237ecf9-e361-41cd-bce7-52bbd74eba0c"
0x28974  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x28979  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2897e  brfalse.s loc_28990
0x28980  ldstr    aACustomEntityD// "A custom entity defined as an activity "...
0x28985  ldc.i4   0x8004F121
0x2898a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2898f  throw
0x28990  ldarg.1
0x28991  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x28996  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_CanBeInCustomEntityAssociation()
0x2899b  brfalse.s loc_289AD
0x2899d  ldstr    aActivitiesCann// "Activities cannot participate in custom"...
0x289a2  ldc.i4   0x80044332
0x289a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x289ac  throw
0x289ad  ldarg.1
0x289ae  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsMailMergeEnabled()
0x289b3  brfalse.s loc_289C5
0x289b5  ldstr    aACustomEntityD_2// "A custom entity defined as an activity "...
0x289ba  ldc.i4   0x8004F124
0x289bf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x289c4  throw
0x289c5  ldarg.1
0x289c6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x289cb  ldstr    aIsreplicated// "isreplicated"
0x289d0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x289d5  brfalse.s loc_28A06
0x289d7  ldarg.1
0x289d8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x289dd  ldstr    aE0a50003706242// "E0A50003-7062-42AB-8A74-95EEEC03C13E"
0x289e2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x289e7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x289ec  brfalse.s loc_28A06
0x289ee  ldarg.1
0x289ef  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_AvailableOffline()
0x289f4  brtrue.s loc_28A06
0x289f6  ldstr    aACustomEntityD_0// "A custom entity defined as an activity "...
0x289fb  ldc.i4   0x8004F122
0x28a00  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x28a05  throw
0x28a06  ldarg.1
0x28a07  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsActivityParty()
0x28a0c  brfalse.s loc_28A4C
0x28a0e  ldarg.1
0x28a0f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x28a14  ldstr    a87e909a7E37840// "87e909a7-e378-407e-92f2-2dab2a6b7ca6"
0x28a19  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x28a1e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28a23  brfalse.s loc_28A4C
0x28a25  ldarg.1
0x28a26  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityId()
0x28a2b  ldstr    aB237ecf9E36141// "b237ecf9-e361-41cd-bce7-52bbd74eba0c"
0x28a30  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x28a35  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28a3a  brfalse.s loc_28A4C
0x28a3c  ldstr    aAnEntityThatIs// "An entity that is defined as an activit"...
0x28a41  ldc.i4   0x80048501
0x28a46  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x28a4b  throw
0x28a4c  ret
```
