# Microsoft.Crm.Metadata.EntityService::ValidateVirtualEntityUpdateInternal

- ea: `0x35e60`
- end: `0x35fcb`
- name: `Microsoft.Crm.Metadata.EntityService::ValidateVirtualEntityUpdateInternal`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x39940`

## callees

- `0x35e60`
- `0x3cb50`
- `0x3cdc0`
- `0x3cde0`
- `0x3cee0`
- `0x3cf00`
- `0x3cfe0`
- `0x3d020`
- `0x3d040`
- `0x3d250`
- `0x3d490`
- `0x3d510`
- `0x3d550`
- `0x3d590`
- `0x3d5b0`
- `0x3d610`
- `0x3d790`
- `0x3d7b0`

## string_xrefs

- `0x35f95`: `cancreatecharts`
- `0x35ee3`: `autocreateaccessteams`
- `0x35efa`: `Is Auto Create Access Teams can not be active for virtual Entity.`
- `0x35fac`: `Cannot create charts for virtual Entity.`

## pseudocode

```c

```

## disassembly

```asm
0x35e60  ldsfld   string [mscorlib]System.String::Empty
0x35e65  pop
0x35e66  ldarg.1
0x35e67  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsAuditEnabled()
0x35e6c  brfalse.s loc_35E79
0x35e6e  ldstr    aIsAuditEnabled// "Is Audit Enabled can not be active for "...
0x35e73  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35e78  throw
0x35e79  ldarg.1
0x35e7a  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsSLAEnabled()
0x35e7f  brfalse.s loc_35E8C
0x35e81  ldstr    aIsSlaEnabledCa// "Is SLA Enabled can not be active for vi"...
0x35e86  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35e8b  throw
0x35e8c  ldarg.1
0x35e8d  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsBusinessProcessEnabled()
0x35e92  brfalse.s loc_35E9F
0x35e94  ldstr    aBusinessProces// "Business process flow cannot be enabled"...
0x35e99  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35e9e  throw
0x35e9f  ldarg.1
0x35ea0  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsBPFEntity()
0x35ea5  brfalse.s loc_35EB2
0x35ea7  ldstr    aAVirtualEntity// "a virtual entity cannot be a bpf entity"
0x35eac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35eb1  throw
0x35eb2  ldarg.1
0x35eb3  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsDuplicateCheckSupported()
0x35eb8  brfalse.s loc_35EC5
0x35eba  ldstr    aIsDuplicateChe// "Is Duplicate Check Supported can not be"...
0x35ebf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35ec4  throw
0x35ec5  ldarg.1
0x35ec6  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsCollaboration()
0x35ecb  brfalse.s loc_35ED8
0x35ecd  ldstr    aIsCollaboratio// "Is Collaboration can not be active for "...
0x35ed2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35ed7  throw
0x35ed8  ldarg.1
0x35ed9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x35ede  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x35ee3  ldstr    aAutocreateacce// "autocreateaccessteams"
0x35ee8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x35eed  brtrue.s loc_35EF7
0x35eef  ldarg.1
0x35ef0  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_AutoCreateAccessTeams()
0x35ef5  br.s     loc_35EF8
0x35ef7  ldc.i4.0
0x35ef8  brfalse.s loc_35F05
0x35efa  ldstr    aIsAutoCreateAc// "Is Auto Create Access Teams can not be "...
0x35eff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35f04  throw
0x35f05  ldarg.1
0x35f06  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_AvailableOffline()
0x35f0b  brfalse.s loc_35F18
0x35f0d  ldstr    aVirtualEntityI// "Virtual Entity is not available for out"...
0x35f12  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35f17  throw
0x35f18  ldarg.1
0x35f19  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsOptimisticConcurrencyRequired()
0x35f1e  brfalse.s loc_35F2B
0x35f20  ldstr    aIsoptimisticco_1// "IsOptimisticConcurrencyRequired can not"...
0x35f25  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35f2a  throw
0x35f2b  ldarg.1
0x35f2c  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_CanOptimisticConcurrencyBeEnabled()
0x35f31  brfalse.s loc_35F3E
0x35f33  ldstr    aCanoptimisticc_1// "CanOptimisticConcurrencyBeEnabled can n"...
0x35f38  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35f3d  throw
0x35f3e  ldarg.1
0x35f3f  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_ChangeTrackingEnabled()
0x35f44  brfalse.s loc_35F51
0x35f46  ldstr    aChangetracking_0// "ChangeTrackingEnabled can not be active"...
0x35f4b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35f50  throw
0x35f51  ldarg.1
0x35f52  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_CanChangeTrackingBeEnabled()
0x35f57  brfalse.s loc_35F64
0x35f59  ldstr    aCanchangetrack_0// "CanChangeTrackingBeEnabled can not be a"...
0x35f5e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35f63  throw
0x35f64  ldarg.1
0x35f65  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsEnabledForExternalChannels()
0x35f6a  brfalse.s loc_35F77
0x35f6c  ldstr    aIsenabledforex_0// "IsEnabledForExternalChannels can not be"...
0x35f71  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35f76  throw
0x35f77  ldarg.1
0x35f78  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsPrivate()
0x35f7d  brfalse.s loc_35F8A
0x35f7f  ldstr    aIsprivateCanNo// "IsPrivate can not be active for virtual"...
0x35f84  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35f89  throw
0x35f8a  ldarg.1
0x35f8b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x35f90  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x35f95  ldstr    aCancreatechart// "cancreatecharts"
0x35f9a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x35f9f  brtrue.s loc_35FA9
0x35fa1  ldarg.1
0x35fa2  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_CanCreateCharts()
0x35fa7  br.s     loc_35FAA
0x35fa9  ldc.i4.0
0x35faa  brfalse.s loc_35FB7
0x35fac  ldstr    aCannotCreateCh// "Cannot create charts for virtual Entity"...
0x35fb1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35fb6  throw
0x35fb7  ldarg.1
0x35fb8  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsEnabledForCharts()
0x35fbd  brfalse.s loc_35FCA
0x35fbf  ldstr    aChartsAreNotEn// "Charts are not enabled for Virtual Enti"...
0x35fc4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35fc9  throw
0x35fca  ret
```
