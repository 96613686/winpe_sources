# Microsoft.Crm.Service.ObjectModel.IncidentService::DecrementAllotment

- ea: `0x2eb0`
- end: `0x3097`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::DecrementAllotment`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c00`

## callees

- `0x2eb0`
- `0x3150`
- `0x3160`

## pseudocode

```c

```

## disassembly

```asm
0x2eb0  ldc.i4.4
0x2eb1  newarr   [mscorlib]System.String
0x2eb6  dup
0x2eb7  ldc.i4.0
0x2eb8  ldstr    aAllotmentsrema// "allotmentsremaining"
0x2ebd  stelem.ref
0x2ebe  dup
0x2ebf  ldc.i4.1
0x2ec0  ldstr    aAllotmentsused// "allotmentsused"
0x2ec5  stelem.ref
0x2ec6  dup
0x2ec7  ldc.i4.2
0x2ec8  ldstr    aTotalallotment// "totalallotments"
0x2ecd  stelem.ref
0x2ece  dup
0x2ecf  ldc.i4.3
0x2ed0  ldstr    aAllotmentsover// "allotmentsoverage"
0x2ed5  stelem.ref
0x2ed6  stloc.0
0x2ed7  ldc.i4.0
0x2ed8  stloc.1
0x2ed9  ldc.i4.0
0x2eda  stloc.2
0x2edb  ldc.i4.0
0x2edc  stloc.3
0x2edd  ldc.i4.0
0x2ede  stloc.s  4
0x2ee0  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::.ctor()
0x2ee5  stloc.s  5
0x2ee7  ldstr    aContractdetail_0// "ContractDetail"
0x2eec  ldarg.3
0x2eed  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2ef2  stloc.s  6
0x2ef4  ldloc.s  6
0x2ef6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2efb  ldloc.0
0x2efc  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2f01  ldarg.1
0x2f02  ldstr    aContractdetail_0// "ContractDetail"
0x2f07  ldarg.3
0x2f08  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2f0d  stloc.s  7
0x2f0f  ldnull
0x2f10  stloc.s  8
0x2f12  ldarg.3
0x2f13  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2f18  stloc.s  0xA
0x2f1a  ldloc.s  5
0x2f1c  ldloc.s  7
0x2f1e  ldloc.s  6
0x2f20  ldarg.3
0x2f21  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2f26  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.ContractDetail
0x2f2b  stloc.s  8
0x2f2d  leave.s  loc_2F3B
0x2f2f  ldloc.s  0xA
0x2f31  brfalse.s loc_2F3A
0x2f33  ldloc.s  0xA
0x2f35  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f3a  endfinally
0x2f3b  ldloc.s  8
0x2f3d  ldstr    aAllotmentsrema// "allotmentsremaining"
0x2f42  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2f47  brfalse.s loc_2F5A
0x2f49  ldc.i4   0x800404F2
0x2f4e  ldc.i4.0
0x2f4f  newarr   [mscorlib]System.Object
0x2f54  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2f59  throw
0x2f5a  ldloc.s  8
0x2f5c  ldstr    aAllotmentsrema// "allotmentsremaining"
0x2f61  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f66  unbox.any [mscorlib]System.Int32
0x2f6b  stloc.1
0x2f6c  ldloc.1
0x2f6d  ldarg.2
0x2f6e  sub
0x2f6f  stloc.1
0x2f70  ldloc.s  8
0x2f72  ldstr    aAllotmentsused// "allotmentsused"
0x2f77  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2f7c  brfalse.s loc_2F8F
0x2f7e  ldc.i4   0x800404F1
0x2f83  ldc.i4.0
0x2f84  newarr   [mscorlib]System.Object
0x2f89  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2f8e  throw
0x2f8f  ldloc.s  8
0x2f91  ldstr    aAllotmentsused// "allotmentsused"
0x2f96  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2f9b  unbox.any [mscorlib]System.Int32
0x2fa0  ldarg.2
0x2fa1  add
0x2fa2  stloc.2
0x2fa3  ldloc.s  8
0x2fa5  ldstr    aTotalallotment// "totalallotments"
0x2faa  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2faf  brfalse.s loc_2FC2
0x2fb1  ldc.i4   0x800404F0
0x2fb6  ldc.i4.0
0x2fb7  newarr   [mscorlib]System.Object
0x2fbc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2fc1  throw
0x2fc2  ldloc.s  8
0x2fc4  ldstr    aTotalallotment// "totalallotments"
0x2fc9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2fce  unbox.any [mscorlib]System.Int32
0x2fd3  stloc.3
0x2fd4  ldarg.3
0x2fd5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2fda  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.ContractDetail::.ctor(valuetype [mscorlib]System.Guid)
0x2fdf  stloc.s  9
0x2fe1  ldloc.s  8
0x2fe3  ldstr    aAllotmentsover// "allotmentsoverage"
0x2fe8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2fed  brfalse.s loc_3004
0x2fef  ldloc.s  9
0x2ff1  ldstr    aAllotmentsover// "allotmentsoverage"
0x2ff6  ldloc.s  4
0x2ff8  box      [mscorlib]System.Int32
0x2ffd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3002  br.s     loc_3017
0x3004  ldloc.s  8
0x3006  ldstr    aAllotmentsover// "allotmentsoverage"
0x300b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3010  unbox.any [mscorlib]System.Int32
0x3015  stloc.s  4
0x3017  ldloc.s  9
0x3019  ldstr    aContractdetail// "contractdetailid"
0x301e  ldarg.1
0x301f  box      [mscorlib]System.Guid
0x3024  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3029  ldloc.2
0x302a  ldloc.3
0x302b  ble.s    loc_3052
0x302d  ldloc.2
0x302e  ldloc.3
0x302f  sub
0x3030  stloc.s  0xB
0x3032  ldloc.1
0x3033  ldloc.s  0xB
0x3035  add
0x3036  stloc.1
0x3037  ldloc.2
0x3038  ldloc.s  0xB
0x303a  sub
0x303b  stloc.2
0x303c  ldloc.s  9
0x303e  ldstr    aAllotmentsover// "allotmentsoverage"
0x3043  ldloc.s  4
0x3045  ldloc.s  0xB
0x3047  add
0x3048  box      [mscorlib]System.Int32
0x304d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3052  ldloc.s  9
0x3054  ldstr    aAllotmentsused// "allotmentsused"
0x3059  ldloc.2
0x305a  box      [mscorlib]System.Int32
0x305f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3064  ldloc.s  9
0x3066  ldstr    aAllotmentsrema// "allotmentsremaining"
0x306b  ldloc.1
0x306c  box      [mscorlib]System.Int32
0x3071  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3076  ldarg.3
0x3077  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x307c  stloc.s  0xA
0x307e  ldloc.s  5
0x3080  ldloc.s  9
0x3082  ldarg.3
0x3083  callvirt instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::InternalUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3088  leave.s  loc_3096
0x308a  ldloc.s  0xA
0x308c  brfalse.s loc_3095
0x308e  ldloc.s  0xA
0x3090  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3095  endfinally
0x3096  ret
```
