# Microsoft.Crm.Service.ObjectModel.ContractService::Expire

- ea: `0x3830`
- end: `0x395c`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::Expire`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x3710`

## callees

- `0x3150`
- `0x3370`
- `0x3830`
- `0x4220`
- `0x42c0`

## pseudocode

```c

```

## disassembly

```asm
0x3830  ldnull
0x3831  stloc.0
0x3832  ldarg.3
0x3833  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3838  stloc.2
0x3839  ldarg.0
0x383a  ldarg.1
0x383b  ldarg.3
0x383c  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract Microsoft.Crm.Service.ObjectModel.ContractService::GetContract(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3841  stloc.0
0x3842  leave.s  loc_384E
0x3844  ldloc.2
0x3845  brfalse.s loc_384D
0x3847  ldloc.2
0x3848  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x384d  endfinally
0x384e  ldloc.0
0x384f  ldstr    aStatecode// "statecode"
0x3854  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3859  unbox.any [mscorlib]System.Int32
0x385e  ldc.i4.5
0x385f  bne.un.s loc_3863
0x3861  ldc.i4.1
0x3862  ret
0x3863  ldloc.0
0x3864  ldstr    aStatecode// "statecode"
0x3869  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x386e  unbox.any [mscorlib]System.Int32
0x3873  ldc.i4.4
0x3874  bne.un.s loc_3887
0x3876  ldc.i4   0x80043203
0x387b  ldc.i4.0
0x387c  newarr   [mscorlib]System.Object
0x3881  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3886  throw
0x3887  ldloc.0
0x3888  ldstr    aExpireson// "expireson"
0x388d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3892  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3897  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x389c  stloc.1
0x389d  ldloc.1
0x389e  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x38a3  stloc.3
0x38a4  ldloca.s 3
0x38a6  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x38ab  ldc.r8   0.0
0x38b4  bgt.un.s loc_3935
0x38b6  ldarg.0
0x38b7  ldloc.0
0x38b8  ldstr    aContractid// "contractid"
0x38bd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x38c2  unbox.any [mscorlib]System.Guid
0x38c7  ldarg.3
0x38c8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetailsNotCanceled(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x38cd  stloc.s  4
0x38cf  ldloc.s  4
0x38d1  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x38d6  ldc.i4.0
0x38d7  ble.s    loc_3946
0x38d9  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::.ctor()
0x38de  stloc.s  5
0x38e0  ldloc.s  4
0x38e2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x38e7  stloc.s  6
0x38e9  br.s     loc_3915
0x38eb  ldloc.s  6
0x38ed  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x38f2  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x38f7  stloc.s  7
0x38f9  ldloc.s  5
0x38fb  ldloc.s  7
0x38fd  ldstr    aContractdetail// "contractdetailid"
0x3902  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3907  unbox.any [mscorlib]System.Guid
0x390c  ldc.i4.m1
0x390d  ldc.i4.1
0x390e  ldarg.3
0x390f  callvirt instance bool Microsoft.Crm.Service.ObjectModel.ContractDetailService::Expire(valuetype [mscorlib]System.Guid contractDetailId, int32 status, bool ignoreContractAndLineStatus, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3914  pop
0x3915  ldloc.s  6
0x3917  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x391c  brtrue.s loc_38EB
0x391e  leave.s  loc_3946
0x3920  ldloc.s  6
0x3922  isinst   [mscorlib]System.IDisposable
0x3927  stloc.s  8
0x3929  ldloc.s  8
0x392b  brfalse.s loc_3934
0x392d  ldloc.s  8
0x392f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3934  endfinally
0x3935  ldc.i4   0x80043203
0x393a  ldc.i4.0
0x393b  newarr   [mscorlib]System.Object
0x3940  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3945  throw
0x3946  ldarg.0
0x3947  ldarg.1
0x3948  ldstr    aContract// "Contract"
0x394d  ldarg.3
0x394e  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3953  ldc.i4.5
0x3954  ldarg.2
0x3955  ldarg.3
0x3956  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x395b  ret
```
