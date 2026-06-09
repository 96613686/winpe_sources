# Microsoft.Crm.Service.ObjectModel.ContractService::ReleaseHold

- ea: `0x3da0`
- end: `0x3f43`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::ReleaseHold`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x3710`

## callees

- `0x3150`
- `0x31c0`
- `0x3370`
- `0x3da0`
- `0x4220`
- `0x42d0`

## pseudocode

```c

```

## disassembly

```asm
0x3da0  ldnull
0x3da1  stloc.0
0x3da2  ldarg.2
0x3da3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3da8  stloc.s  6
0x3daa  ldarg.0
0x3dab  ldarg.1
0x3dac  ldarg.2
0x3dad  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract Microsoft.Crm.Service.ObjectModel.ContractService::GetContract(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3db2  stloc.0
0x3db3  leave.s  loc_3DC1
0x3db5  ldloc.s  6
0x3db7  brfalse.s loc_3DC0
0x3db9  ldloc.s  6
0x3dbb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3dc0  endfinally
0x3dc1  ldloc.0
0x3dc2  ldstr    aStatecode// "statecode"
0x3dc7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3dcc  unbox.any [mscorlib]System.Int32
0x3dd1  ldc.i4.3
0x3dd2  beq.s    loc_3DE5
0x3dd4  ldc.i4   0x80043203
0x3dd9  ldc.i4.0
0x3dda  newarr   [mscorlib]System.Object
0x3ddf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3de4  throw
0x3de5  ldloc.0
0x3de6  ldstr    aActiveon// "activeon"
0x3deb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3df0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3df5  stloc.1
0x3df6  ldloc.0
0x3df7  ldstr    aExpireson// "expireson"
0x3dfc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3e01  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3e06  stloc.2
0x3e07  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x3e0c  stloc.3
0x3e0d  ldloc.0
0x3e0e  ldstr    aCancelon// "cancelon"
0x3e13  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3e18  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3e1d  stloc.s  4
0x3e1f  ldc.i4.5
0x3e20  stloc.s  5
0x3e22  ldloc.s  4
0x3e24  ldnull
0x3e25  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::op_Inequality(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3e2a  brfalse.s loc_3E4D
0x3e2c  ldloc.3
0x3e2d  ldloc.s  4
0x3e2f  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3e34  stloc.s  7
0x3e36  ldloca.s 7
0x3e38  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3e3d  ldc.r8   0.0
0x3e46  blt.un.s loc_3E4D
0x3e48  ldc.i4.4
0x3e49  stloc.s  5
0x3e4b  br.s     loc_3E8B
0x3e4d  ldloc.1
0x3e4e  ldloc.3
0x3e4f  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3e54  stloc.s  7
0x3e56  ldloca.s 7
0x3e58  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3e5d  ldc.r8   0.0
0x3e66  ble.un.s loc_3E6D
0x3e68  ldc.i4.1
0x3e69  stloc.s  5
0x3e6b  br.s     loc_3E8B
0x3e6d  ldloc.2
0x3e6e  ldloc.3
0x3e6f  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3e74  stloc.s  7
0x3e76  ldloca.s 7
0x3e78  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3e7d  ldc.r8   0.0
0x3e86  ble.un.s loc_3E8B
0x3e88  ldc.i4.2
0x3e89  stloc.s  5
0x3e8b  ldloc.s  5
0x3e8d  ldc.i4.4
0x3e8e  beq.s    loc_3E98
0x3e90  ldloc.s  5
0x3e92  ldc.i4.5
0x3e93  bne.un   loc_3F2C
0x3e98  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::.ctor()
0x3e9d  stloc.s  8
0x3e9f  ldarg.0
0x3ea0  ldloc.0
0x3ea1  ldstr    aContractid// "contractid"
0x3ea6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3eab  unbox.any [mscorlib]System.Guid
0x3eb0  ldarg.2
0x3eb1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetails(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3eb6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3ebb  stloc.s  9
0x3ebd  br.s     loc_3F0C
0x3ebf  ldloc.s  9
0x3ec1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3ec6  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x3ecb  stloc.s  0xA
0x3ecd  ldloc.s  5
0x3ecf  ldc.i4.4
0x3ed0  bne.un.s loc_3EF0
0x3ed2  ldloc.s  8
0x3ed4  ldloc.s  0xA
0x3ed6  ldstr    aContractdetail// "contractdetailid"
0x3edb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3ee0  unbox.any [mscorlib]System.Guid
0x3ee5  ldc.i4.m1
0x3ee6  ldc.i4.1
0x3ee7  ldarg.2
0x3ee8  callvirt instance bool Microsoft.Crm.Service.ObjectModel.ContractDetailService::Cancel(valuetype [mscorlib]System.Guid contractDetailId, int32 status, bool ignoreContractAndLineStatus, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3eed  pop
0x3eee  br.s     loc_3F0C
0x3ef0  ldloc.s  8
0x3ef2  ldloc.s  0xA
0x3ef4  ldstr    aContractdetail// "contractdetailid"
0x3ef9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3efe  unbox.any [mscorlib]System.Guid
0x3f03  ldc.i4.m1
0x3f04  ldc.i4.1
0x3f05  ldarg.2
0x3f06  callvirt instance bool Microsoft.Crm.Service.ObjectModel.ContractDetailService::Expire(valuetype [mscorlib]System.Guid contractDetailId, int32 status, bool ignoreContractAndLineStatus, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3f0b  pop
0x3f0c  ldloc.s  9
0x3f0e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3f13  brtrue.s loc_3EBF
0x3f15  leave.s  loc_3F2C
0x3f17  ldloc.s  9
0x3f19  isinst   [mscorlib]System.IDisposable
0x3f1e  stloc.s  0xB
0x3f20  ldloc.s  0xB
0x3f22  brfalse.s loc_3F2B
0x3f24  ldloc.s  0xB
0x3f26  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f2b  endfinally
0x3f2c  ldarg.0
0x3f2d  ldarg.1
0x3f2e  ldstr    aContract// "Contract"
0x3f33  ldarg.2
0x3f34  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3f39  ldloc.s  5
0x3f3b  ldc.i4.m1
0x3f3c  ldarg.2
0x3f3d  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3f42  ret
```
