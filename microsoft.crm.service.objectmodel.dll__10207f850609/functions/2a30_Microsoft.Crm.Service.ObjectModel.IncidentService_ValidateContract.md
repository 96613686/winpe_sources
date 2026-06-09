# Microsoft.Crm.Service.ObjectModel.IncidentService::ValidateContract

- ea: `0x2a30`
- end: `0x2bb4`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::ValidateContract`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x2a30`
- `0x3150`
- `0x3630`

## string_xrefs

- `0x2ad2`: `Contract state is not active, the case can not be created against this contract.`
- `0x2b6a`: `Contract line item state is cancelled or expired, the case can not be created against this contract line item.`
- `0x2ba3`: `The contract does not have enough allotments. The case can not be created against this contract.`

## pseudocode

```c

```

## disassembly

```asm
0x2a30  ldarg.1
0x2a31  ldstr    aContractid// "contractid"
0x2a36  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x2a3b  brfalse.s loc_2A3E
0x2a3d  ret
0x2a3e  ldarg.1
0x2a3f  ldstr    aContractid// "contractid"
0x2a44  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x2a49  unbox.any [mscorlib]System.Guid
0x2a4e  stloc.0
0x2a4f  ldarg.1
0x2a50  ldstr    aContractdetail// "contractdetailid"
0x2a55  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x2a5a  brfalse.s loc_2A6D
0x2a5c  ldc.i4   0x80044401
0x2a61  ldc.i4.0
0x2a62  newarr   [mscorlib]System.Object
0x2a67  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2a6c  throw
0x2a6d  ldc.i4.2
0x2a6e  newarr   [mscorlib]System.String
0x2a73  dup
0x2a74  ldc.i4.0
0x2a75  ldstr    aStatecode// "statecode"
0x2a7a  stelem.ref
0x2a7b  dup
0x2a7c  ldc.i4.1
0x2a7d  ldstr    aAllotmenttypec// "allotmenttypecode"
0x2a82  stelem.ref
0x2a83  stloc.1
0x2a84  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractService::.ctor()
0x2a89  ldstr    aContract// "Contract"
0x2a8e  ldarg.2
0x2a8f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2a94  stloc.2
0x2a95  ldloc.2
0x2a96  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2a9b  ldloc.1
0x2a9c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2aa1  ldloc.0
0x2aa2  ldstr    aContract// "Contract"
0x2aa7  ldarg.2
0x2aa8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2aad  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x2ab2  ldloc.2
0x2ab3  ldarg.2
0x2ab4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2ab9  isinst   [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract
0x2abe  stloc.3
0x2abf  ldloc.3
0x2ac0  ldstr    aStatecode// "statecode"
0x2ac5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2aca  unbox.any [mscorlib]System.Int32
0x2acf  ldc.i4.2
0x2ad0  beq.s    loc_2AE2
0x2ad2  ldstr    aContractStateI// "Contract state is not active, the case "...
0x2ad7  ldc.i4   0x80044400
0x2adc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2ae1  throw
0x2ae2  ldarg.1
0x2ae3  ldstr    aContractdetail// "contractdetailid"
0x2ae8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x2aed  unbox.any [mscorlib]System.Guid
0x2af2  stloc.s  4
0x2af4  ldc.i4.3
0x2af5  newarr   [mscorlib]System.String
0x2afa  dup
0x2afb  ldc.i4.0
0x2afc  ldstr    aContractid// "contractid"
0x2b01  stelem.ref
0x2b02  dup
0x2b03  ldc.i4.1
0x2b04  ldstr    aStatecode// "statecode"
0x2b09  stelem.ref
0x2b0a  dup
0x2b0b  ldc.i4.2
0x2b0c  ldstr    aAllotmentsrema// "allotmentsremaining"
0x2b11  stelem.ref
0x2b12  stloc.s  5
0x2b14  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::.ctor()
0x2b19  ldstr    aContractdetail_0// "ContractDetail"
0x2b1e  ldarg.2
0x2b1f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2b24  stloc.s  6
0x2b26  ldloc.s  6
0x2b28  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2b2d  ldloc.s  5
0x2b2f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2b34  ldloc.s  4
0x2b36  ldstr    aContractdetail_0// "ContractDetail"
0x2b3b  ldarg.2
0x2b3c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2b41  ldloc.s  6
0x2b43  ldarg.2
0x2b44  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2b49  isinst   [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.ContractDetail
0x2b4e  dup
0x2b4f  ldstr    aStatecode// "statecode"
0x2b54  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b59  unbox.any [mscorlib]System.Int32
0x2b5e  stloc.s  7
0x2b60  ldloc.s  7
0x2b62  ldc.i4.2
0x2b63  beq.s    loc_2B6A
0x2b65  ldloc.s  7
0x2b67  ldc.i4.3
0x2b68  bne.un.s loc_2B7A
0x2b6a  ldstr    aContractLineIt// "Contract line item state is cancelled o"...
0x2b6f  ldc.i4   0x8004440D
0x2b74  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2b79  throw
0x2b7a  ldstr    aAllotmentsrema// "allotmentsremaining"
0x2b7f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b84  unbox.any [mscorlib]System.Int32
0x2b89  stloc.s  8
0x2b8b  ldloc.3
0x2b8c  ldstr    aAllotmenttypec// "allotmenttypecode"
0x2b91  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b96  unbox.any [mscorlib]System.Int32
0x2b9b  ldc.i4.3
0x2b9c  beq.s    loc_2BB3
0x2b9e  ldloc.s  8
0x2ba0  ldc.i4.0
0x2ba1  bgt.s    loc_2BB3
0x2ba3  ldstr    aTheContractDoe// "The contract does not have enough allot"...
0x2ba8  ldc.i4   0x80044403
0x2bad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2bb2  throw
0x2bb3  ret
```
