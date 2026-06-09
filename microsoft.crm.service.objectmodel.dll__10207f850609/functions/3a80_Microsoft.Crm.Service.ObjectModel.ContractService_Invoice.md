# Microsoft.Crm.Service.ObjectModel.ContractService::Invoice

- ea: `0x3a80`
- end: `0x3d27`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::Invoice`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x3710`

## callees

- `0x3150`
- `0x3370`
- `0x3490`
- `0x3a80`
- `0x3f50`
- `0x4220`
- `0x42d0`
- `0x42e0`
- `0x43a0`

## string_xrefs

- `0x3aae`: `contracttemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x3a80  ldarg.0
0x3a81  ldarg.1
0x3a82  ldarg.2
0x3a83  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract Microsoft.Crm.Service.ObjectModel.ContractService::GetContract(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3a88  stloc.0
0x3a89  ldloc.0
0x3a8a  ldstr    aStatecode// "statecode"
0x3a8f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3a94  unbox.any [mscorlib]System.Int32
0x3a99  brfalse.s loc_3AAC
0x3a9b  ldc.i4   0x80043203
0x3aa0  ldc.i4.0
0x3aa1  newarr   [mscorlib]System.Object
0x3aa6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3aab  throw
0x3aac  ldarg.0
0x3aad  ldloc.0
0x3aae  ldstr    aContracttempla// "contracttemplateid"
0x3ab3  ldc.i4   0x80043206
0x3ab8  call     instance void Microsoft.Crm.Service.ObjectModel.ContractService::ValidateExistance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, string attributeName, int32 errorCode)
0x3abd  ldarg.0
0x3abe  ldloc.0
0x3abf  ldstr    aCustomerid// "customerid"
0x3ac4  ldc.i4   0x8004320D
0x3ac9  call     instance void Microsoft.Crm.Service.ObjectModel.ContractService::ValidateExistance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, string attributeName, int32 errorCode)
0x3ace  ldarg.0
0x3acf  ldloc.0
0x3ad0  ldstr    aBillingcustome// "billingcustomerid"
0x3ad5  ldc.i4   0x80043210
0x3ada  call     instance void Microsoft.Crm.Service.ObjectModel.ContractService::ValidateExistance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, string attributeName, int32 errorCode)
0x3adf  ldarg.0
0x3ae0  ldloc.0
0x3ae1  ldstr    aBillingstarton// "billingstarton"
0x3ae6  ldc.i4   0x80040239
0x3aeb  call     instance void Microsoft.Crm.Service.ObjectModel.ContractService::ValidateExistance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, string attributeName, int32 errorCode)
0x3af0  ldarg.0
0x3af1  ldloc.0
0x3af2  ldstr    aBillingendon// "billingendon"
0x3af7  ldc.i4   0x80040239
0x3afc  call     instance void Microsoft.Crm.Service.ObjectModel.ContractService::ValidateExistance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, string attributeName, int32 errorCode)
0x3b01  ldarg.0
0x3b02  ldloc.0
0x3b03  ldstr    aContractnumber// "contractnumber"
0x3b08  ldc.i4   0x80040203
0x3b0d  call     instance void Microsoft.Crm.Service.ObjectModel.ContractService::ValidateExistance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, string attributeName, int32 errorCode)
0x3b12  ldloc.0
0x3b13  ldstr    aActiveon// "activeon"
0x3b18  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3b1d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3b22  stloc.1
0x3b23  ldloc.0
0x3b24  ldstr    aExpireson// "expireson"
0x3b29  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3b2e  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3b33  stloc.2
0x3b34  ldloc.2
0x3b35  ldloc.1
0x3b36  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3b3b  stloc.s  8
0x3b3d  ldloca.s 8
0x3b3f  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3b44  ldc.r8   0.0
0x3b4d  bgt.un.s loc_3B60
0x3b4f  ldc.i4   0x80043202
0x3b54  ldc.i4.0
0x3b55  newarr   [mscorlib]System.Object
0x3b5a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3b5f  throw
0x3b60  ldloc.0
0x3b61  ldstr    aBillingstarton// "billingstarton"
0x3b66  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3b6b  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3b70  stloc.3
0x3b71  ldloc.0
0x3b72  ldstr    aBillingendon// "billingendon"
0x3b77  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3b7c  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3b81  ldloc.3
0x3b82  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3b87  stloc.s  8
0x3b89  ldloca.s 8
0x3b8b  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3b90  ldc.r8   0.0
0x3b99  bgt.un.s loc_3BAC
0x3b9b  ldc.i4   0x80043202
0x3ba0  ldc.i4.0
0x3ba1  newarr   [mscorlib]System.Object
0x3ba6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3bab  throw
0x3bac  ldarg.0
0x3bad  ldloc.0
0x3bae  ldstr    aContractid// "contractid"
0x3bb3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3bb8  unbox.any [mscorlib]System.Guid
0x3bbd  ldarg.2
0x3bbe  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetails(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3bc3  stloc.s  4
0x3bc5  ldloc.s  4
0x3bc7  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x3bcc  brtrue.s loc_3BDF
0x3bce  ldc.i4   0x8004320C
0x3bd3  ldc.i4.0
0x3bd4  newarr   [mscorlib]System.Object
0x3bd9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3bde  throw
0x3bdf  ldarg.0
0x3be0  ldloc.0
0x3be1  ldstr    aContractid// "contractid"
0x3be6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3beb  unbox.any [mscorlib]System.Guid
0x3bf0  ldc.i4.2
0x3bf1  newarr   [mscorlib]System.String
0x3bf6  dup
0x3bf7  ldc.i4.0
0x3bf8  ldstr    aActiveon// "activeon"
0x3bfd  stelem.ref
0x3bfe  dup
0x3bff  ldc.i4.1
0x3c00  ldstr    aExpireson// "expireson"
0x3c05  stelem.ref
0x3c06  ldc.i4.0
0x3c07  ldarg.2
0x3c08  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetails(valuetype [mscorlib]System.Guid contractId, string[] columns, bool allColumns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3c0d  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::.ctor()
0x3c12  stloc.s  5
0x3c14  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3c19  stloc.s  9
0x3c1b  br.s     loc_3C36
0x3c1d  ldloc.s  9
0x3c1f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3c24  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x3c29  stloc.s  0xA
0x3c2b  ldloc.s  5
0x3c2d  ldloc.s  0xA
0x3c2f  ldloc.0
0x3c30  ldc.i4.0
0x3c31  callvirt instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::ValidateActiveExpireDates(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity contractDetail, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity contract, bool required)
0x3c36  ldloc.s  9
0x3c38  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3c3d  brtrue.s loc_3C1D
0x3c3f  leave.s  loc_3C56
0x3c41  ldloc.s  9
0x3c43  isinst   [mscorlib]System.IDisposable
0x3c48  stloc.s  0xB
0x3c4a  ldloc.s  0xB
0x3c4c  brfalse.s loc_3C55
0x3c4e  ldloc.s  0xB
0x3c50  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3c55  endfinally
0x3c56  ldarg.0
0x3c57  ldloc.0
0x3c58  ldstr    aContractnumber// "contractnumber"
0x3c5d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c62  castclass [mscorlib]System.String
0x3c67  ldloc.1
0x3c68  ldloc.2
0x3c69  ldarg.2
0x3c6a  call     instance void Microsoft.Crm.Service.ObjectModel.ContractService::ValidateRenewedContractActiveExpireDates(string contractNumber, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime active, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime expire, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3c6f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x3c74  stloc.s  6
0x3c76  ldc.i4.5
0x3c77  stloc.s  7
0x3c79  ldloc.s  6
0x3c7b  ldloc.1
0x3c7c  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3c81  stloc.s  8
0x3c83  ldloca.s 8
0x3c85  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3c8a  ldc.r8   0.0
0x3c93  bge.un.s loc_3C9A
0x3c95  ldc.i4.1
0x3c96  stloc.s  7
0x3c98  br.s     loc_3D10
0x3c9a  ldloc.s  6
0x3c9c  ldloc.2
0x3c9d  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3ca2  stloc.s  8
0x3ca4  ldloca.s 8
0x3ca6  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3cab  ldc.r8   0.0
0x3cb4  bge.un.s loc_3CBB
0x3cb6  ldc.i4.2
0x3cb7  stloc.s  7
0x3cb9  br.s     loc_3D10
0x3cbb  ldloc.s  4
0x3cbd  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3cc2  stloc.s  9
0x3cc4  br.s     loc_3CF0
0x3cc6  ldloc.s  9
0x3cc8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3ccd  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x3cd2  stloc.s  0xC
0x3cd4  ldloc.s  5
0x3cd6  ldloc.s  0xC
0x3cd8  ldstr    aContractdetail// "contractdetailid"
0x3cdd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3ce2  unbox.any [mscorlib]System.Guid
0x3ce7  ldc.i4.m1
0x3ce8  ldc.i4.1
0x3ce9  ldarg.2
0x3cea  callvirt instance bool Microsoft.Crm.Service.ObjectModel.ContractDetailService::Expire(valuetype [mscorlib]System.Guid contractDetailId, int32 status, bool ignoreContractAndLineStatus, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3cef  pop
0x3cf0  ldloc.s  9
0x3cf2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3cf7  brtrue.s loc_3CC6
0x3cf9  leave.s  loc_3D10
0x3cfb  ldloc.s  9
0x3cfd  isinst   [mscorlib]System.IDisposable
0x3d02  stloc.s  0xB
0x3d04  ldloc.s  0xB
0x3d06  brfalse.s loc_3D0F
0x3d08  ldloc.s  0xB
0x3d0a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d0f  endfinally
0x3d10  ldarg.0
0x3d11  ldarg.1
0x3d12  ldstr    aContract// "Contract"
0x3d17  ldarg.2
0x3d18  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3d1d  ldloc.s  7
0x3d1f  ldc.i4.m1
0x3d20  ldarg.2
0x3d21  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3d26  ret
```
