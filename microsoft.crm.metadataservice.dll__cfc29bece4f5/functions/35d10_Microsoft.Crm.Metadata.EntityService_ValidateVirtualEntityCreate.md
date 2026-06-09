# Microsoft.Crm.Metadata.EntityService::ValidateVirtualEntityCreate

- ea: `0x35d10`
- end: `0x35e5b`
- name: `Microsoft.Crm.Metadata.EntityService::ValidateVirtualEntityCreate`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x359c0`

## callees

- `0x2cb30`
- `0x2cc00`
- `0x2cc30`
- `0x2cc50`
- `0x2cd10`
- `0x2cd30`
- `0x2ce50`
- `0x2ce70`
- `0x2ced0`
- `0x2cef0`
- `0x2cf10`
- `0x2d350`
- `0x2d3b0`
- `0x2d3f0`
- `0x2d430`
- `0x2d4f0`
- `0x2d510`
- `0x35d10`

## string_xrefs

- `0x35da4`: `Is Auto Create Access Teams can not be active for virtual Entity.`
- `0x35e3c`: `Cannot create charts for virtual Entity.`

## pseudocode

```c

```

## disassembly

```asm
0x35d10  ldsfld   string [mscorlib]System.String::Empty
0x35d15  pop
0x35d16  ldarg.1
0x35d17  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x35d1c  ldc.i4.8
0x35d1d  beq.s    loc_35D2A
0x35d1f  ldstr    aVirtualEntitie// "Virtual entities can only be organizati"...
0x35d24  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35d29  throw
0x35d2a  ldarg.1
0x35d2b  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsAuditEnabled()
0x35d30  brfalse.s loc_35D3D
0x35d32  ldstr    aIsAuditEnabled// "Is Audit Enabled can not be active for "...
0x35d37  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35d3c  throw
0x35d3d  ldarg.1
0x35d3e  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsSLAEnabled()
0x35d43  brfalse.s loc_35D50
0x35d45  ldstr    aIsSlaEnabledCa// "Is SLA Enabled can not be active for vi"...
0x35d4a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35d4f  throw
0x35d50  ldarg.1
0x35d51  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBusinessProcessEnabled()
0x35d56  brfalse.s loc_35D63
0x35d58  ldstr    aBusinessProces// "Business process flow cannot be enabled"...
0x35d5d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35d62  throw
0x35d63  ldarg.1
0x35d64  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBPFEntity()
0x35d69  brfalse.s loc_35D76
0x35d6b  ldstr    aAVirtualEntity// "a virtual entity cannot be a bpf entity"
0x35d70  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35d75  throw
0x35d76  ldarg.1
0x35d77  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsDuplicateCheckSupported()
0x35d7c  brfalse.s loc_35D89
0x35d7e  ldstr    aIsDuplicateChe// "Is Duplicate Check Supported can not be"...
0x35d83  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35d88  throw
0x35d89  ldarg.1
0x35d8a  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsCollaboration()
0x35d8f  brfalse.s loc_35D9C
0x35d91  ldstr    aIsCollaboratio// "Is Collaboration can not be active for "...
0x35d96  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35d9b  throw
0x35d9c  ldarg.1
0x35d9d  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_AutoCreateAccessTeams()
0x35da2  brfalse.s loc_35DAF
0x35da4  ldstr    aIsAutoCreateAc// "Is Auto Create Access Teams can not be "...
0x35da9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35dae  throw
0x35daf  ldarg.1
0x35db0  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_AvailableOffline()
0x35db5  brfalse.s loc_35DC2
0x35db7  ldstr    aVirtualEntityI// "Virtual Entity is not available for out"...
0x35dbc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35dc1  throw
0x35dc2  ldarg.1
0x35dc3  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsOptimisticConcurrencyRequired()
0x35dc8  brfalse.s loc_35DD5
0x35dca  ldstr    aIsoptimisticco_1// "IsOptimisticConcurrencyRequired can not"...
0x35dcf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35dd4  throw
0x35dd5  ldarg.1
0x35dd6  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_CanOptimisticConcurrencyBeEnabled()
0x35ddb  brfalse.s loc_35DE8
0x35ddd  ldstr    aCanoptimisticc_1// "CanOptimisticConcurrencyBeEnabled can n"...
0x35de2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35de7  throw
0x35de8  ldarg.1
0x35de9  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_ChangeTrackingEnabled()
0x35dee  brfalse.s loc_35DFB
0x35df0  ldstr    aChangetracking_0// "ChangeTrackingEnabled can not be active"...
0x35df5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35dfa  throw
0x35dfb  ldarg.1
0x35dfc  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_CanChangeTrackingBeEnabled()
0x35e01  brfalse.s loc_35E0E
0x35e03  ldstr    aCanchangetrack_0// "CanChangeTrackingBeEnabled can not be a"...
0x35e08  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35e0d  throw
0x35e0e  ldarg.1
0x35e0f  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsEnabledForExternalChannels()
0x35e14  brfalse.s loc_35E21
0x35e16  ldstr    aIsenabledforex_0// "IsEnabledForExternalChannels can not be"...
0x35e1b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35e20  throw
0x35e21  ldarg.1
0x35e22  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsPrivate()
0x35e27  brfalse.s loc_35E34
0x35e29  ldstr    aIsprivateCanNo// "IsPrivate can not be active for virtual"...
0x35e2e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35e33  throw
0x35e34  ldarg.1
0x35e35  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_CanCreateCharts()
0x35e3a  brfalse.s loc_35E47
0x35e3c  ldstr    aCannotCreateCh// "Cannot create charts for virtual Entity"...
0x35e41  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35e46  throw
0x35e47  ldarg.1
0x35e48  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsEnabledForCharts()
0x35e4d  brfalse.s loc_35E5A
0x35e4f  ldstr    aChartsAreNotEn// "Charts are not enabled for Virtual Enti"...
0x35e54  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x35e59  throw
0x35e5a  ret
```
