# Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::Create_1

- ea: `0x17d70`
- end: `0x17eb2`
- name: `Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::Create_1`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x17d50`

## callees

- `0x17830`
- `0x17940`
- `0x17980`
- `0x179c0`
- `0x17a00`
- `0x17a40`
- `0x17a80`
- `0x17ac0`
- `0x17b00`
- `0x17b50`
- `0x17ba0`
- `0x17be0`
- `0x17d70`
- `0x182c0`
- `0x18790`
- `0x19e90`
- `0x1a3b0`
- `0x1e9b0`
- `0x1f550`
- `0x22b70`
- `0x23260`

## string_xrefs

- `0x17e90`: `Create`
- `0x17e95`: `D:\a\1\s\src\CrmLive\Admin\AvailabilityGroup\CrmAvailabilityGroupService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x17d70  ldarg.1
0x17d71  ldstr    aAvailabilitygr_3// "AvailabilityGroup Name"
0x17d76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17d7b  ldarg.2
0x17d7c  ldstr    aDatacenterName// "datacenter name"
0x17d81  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17d86  ldarg.3
0x17d87  ldstr    aPrimaryName// "primary name"
0x17d8c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17d91  ldarg.s  4
0x17d93  ldstr    aSyncName// "sync name"
0x17d98  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17d9d  ldarg.s  8
0x17d9f  brtrue.s loc_17DAF
0x17da1  ldarg.s  7
0x17da3  ldstr    aScalegroup_0// "scalegroup"
0x17da8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x17dad  br.s     loc_17DD5
0x17daf  ldarg.s  7
0x17db1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x17db6  brtrue.s loc_17DD5
0x17db8  ldstr    aTheScalegroupP// "The scalegroup parameter is not valid f"...
0x17dbd  ldarga.s 8
0x17dbf  constrained. Microsoft.Crm.Admin.AdminService.AvailabilityGroupType
0x17dc5  callvirt instance string [mscorlib]System.Object::ToString()
0x17dca  call     string [mscorlib]System.String::Concat(string, string)
0x17dcf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x17dd4  throw
0x17dd5  ldarg.s  8
0x17dd7  ldc.i4.3
0x17dd8  bne.un.s loc_17DF2
0x17dda  ldarg.0
0x17ddb  call     instance class Microsoft.Crm.Admin.AdminService.AvailabilityGroupData Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::RetrieveGeoAvailabilityGroup()
0x17de0  brfalse.s loc_17DF2
0x17de2  ldstr    aAvailabilitygr_1// "AvailabilityGroup"
0x17de7  ldstr    aGeo// "Geo"
0x17dec  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBDuplicateRecord(string objectType, object value)
0x17df1  throw
0x17df2  newobj   instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::.ctor()
0x17df7  stloc.0
0x17df8  ldloc.0
0x17df9  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x17dfe  callvirt instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::set_Id(valuetype [mscorlib]System.Guid value)
0x17e03  ldloc.0
0x17e04  ldarg.1
0x17e05  callvirt instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::set_Name(string value)
0x17e0a  ldloc.0
0x17e0b  ldarg.3
0x17e0c  callvirt instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::set_PrimaryServer(string value)
0x17e11  ldloc.0
0x17e12  ldarg.s  4
0x17e14  callvirt instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::set_SyncReplica(string value)
0x17e19  ldloc.0
0x17e1a  ldarg.s  5
0x17e1c  callvirt instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::set_AsyncReplica1(string value)
0x17e21  ldloc.0
0x17e22  ldarg.s  6
0x17e24  callvirt instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::set_AsyncReplica2(string value)
0x17e29  ldloc.0
0x17e2a  ldarg.s  8
0x17e2c  callvirt instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::set_AvailabilityGroupType(valuetype Microsoft.Crm.Admin.AdminService.AvailabilityGroupType value)
0x17e31  ldarg.s  9
0x17e33  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x17e38  brtrue.s loc_17E4C
0x17e3a  ldloc.0
0x17e3b  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmStorageGroupService::.ctor()
0x17e40  ldarg.s  9
0x17e42  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmStorageGroupService::GetIdFromName(string storageGroupName)
0x17e47  callvirt instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::set_StorageGroupId(valuetype [mscorlib]System.Guid value)
0x17e4c  ldarg.s  7
0x17e4e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x17e53  brtrue.s loc_17E69
0x17e55  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::.ctor()
0x17e5a  stloc.2
0x17e5b  ldloc.0
0x17e5c  ldloc.2
0x17e5d  ldarg.s  7
0x17e5f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::GetIdFromName(string scaleGroupName)
0x17e64  callvirt instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::set_ScaleGroupId(valuetype [mscorlib]System.Guid value)
0x17e69  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmDatacenterService::.ctor()
0x17e6e  stloc.1
0x17e6f  ldloc.0
0x17e70  ldloc.1
0x17e71  ldarg.2
0x17e72  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmDatacenterService::GetIdFromName(string datacenterName)
0x17e77  callvirt instance void Microsoft.Crm.Admin.AdminService.AvailabilityGroupData::set_DatacenterId(valuetype [mscorlib]System.Guid value)
0x17e7c  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x17e81  stloc.3
0x17e82  ldloc.3
0x17e83  ldstr    aAvailabilitygr_4// "AvailabilityGroups"
0x17e88  ldloc.0
0x17e89  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x17e8e  ldc.i4.s 0x7C
0x17e90  ldstr    aCreate// "Create"
0x17e95  ldstr    aDA1SSrcCrmlive_33// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Avail"...
0x17e9a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x17e9f  pop
0x17ea0  ldloc.0
0x17ea1  stloc.s  4
0x17ea3  leave.s  loc_17EAF
0x17ea5  ldloc.3
0x17ea6  brfalse.s loc_17EAE
0x17ea8  ldloc.3
0x17ea9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17eae  endfinally
0x17eaf  ldloc.s  4
0x17eb1  ret
```
