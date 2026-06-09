# Microsoft.Crm.Service.ObjectModel.ContractDetailService::Cancel

- ea: `0x31c0`
- end: `0x336c`
- name: `Microsoft.Crm.Service.ObjectModel.ContractDetailService::Cancel`
- size: `428`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x3180`
- `0x3da0`
- `0x4040`

## callees

- `0x31c0`
- `0x33f0`
- `0x35a0`
- `0x3630`
- `0x36c0`
- `0x4220`

## pseudocode

```c

```

## disassembly

```asm
0x31c0  ldnull
0x31c1  stloc.0
0x31c2  ldarg.s  4
0x31c4  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31c9  stloc.s  4
0x31cb  ldarg.0
0x31cc  ldarg.1
0x31cd  ldarg.s  4
0x31cf  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.ContractDetail Microsoft.Crm.Service.ObjectModel.ContractDetailService::GetContractDetail(valuetype [mscorlib]System.Guid contractDetailId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31d4  stloc.0
0x31d5  leave.s  loc_31E3
0x31d7  ldloc.s  4
0x31d9  brfalse.s loc_31E2
0x31db  ldloc.s  4
0x31dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31e2  endfinally
0x31e3  ldloc.0
0x31e4  ldstr    aStatecode// "statecode"
0x31e9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x31ee  unbox.any [mscorlib]System.Int32
0x31f3  ldc.i4.2
0x31f4  bne.un.s loc_31F8
0x31f6  ldc.i4.1
0x31f7  ret
0x31f8  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractService::.ctor()
0x31fd  dup
0x31fe  ldloc.0
0x31ff  ldstr    aContractid// "contractid"
0x3204  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3209  unbox.any [mscorlib]System.Guid
0x320e  ldarg.s  4
0x3210  callvirt instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract Microsoft.Crm.Service.ObjectModel.ContractService::GetContract(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3215  stloc.1
0x3216  ldarg.3
0x3217  brtrue.s loc_3285
0x3219  ldloc.1
0x321a  ldstr    aStatecode// "statecode"
0x321f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3224  unbox.any [mscorlib]System.Int32
0x3229  ldc.i4.4
0x322a  beq.s    loc_3262
0x322c  ldloc.1
0x322d  ldstr    aStatecode// "statecode"
0x3232  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3237  unbox.any [mscorlib]System.Int32
0x323c  ldc.i4.1
0x323d  beq.s    loc_3262
0x323f  ldloc.1
0x3240  ldstr    aStatecode// "statecode"
0x3245  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x324a  unbox.any [mscorlib]System.Int32
0x324f  ldc.i4.2
0x3250  beq.s    loc_3262
0x3252  ldstr    aTheContractLin// "The contract line item cannot be cancel"...
0x3257  ldc.i4   0x80043203
0x325c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3261  throw
0x3262  ldloc.0
0x3263  ldstr    aStatecode// "statecode"
0x3268  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x326d  unbox.any [mscorlib]System.Int32
0x3272  ldc.i4.3
0x3273  bne.un.s loc_3285
0x3275  ldstr    aTheContractLin_0// "The contract line item cannot be cancel"...
0x327a  ldc.i4   0x80043204
0x327f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3284  throw
0x3285  ldarg.s  4
0x3287  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x328c  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract::.ctor(valuetype [mscorlib]System.Guid)
0x3291  stloc.2
0x3292  ldloc.2
0x3293  ldstr    aContractid// "contractid"
0x3298  ldloc.0
0x3299  ldstr    aContractid// "contractid"
0x329e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32a3  unbox.any [mscorlib]System.Guid
0x32a8  box      [mscorlib]System.Guid
0x32ad  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x32b2  ldloc.2
0x32b3  ldstr    aTotalprice// "totalprice"
0x32b8  ldloc.1
0x32b9  ldstr    aTotalprice// "totalprice"
0x32be  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32c3  unbox.any [mscorlib]System.Decimal
0x32c8  ldloc.0
0x32c9  ldstr    aPrice// "price"
0x32ce  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32d3  unbox.any [mscorlib]System.Decimal
0x32d8  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Subtraction(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x32dd  box      [mscorlib]System.Decimal
0x32e2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x32e7  ldloc.2
0x32e8  ldstr    aTotaldiscount// "totaldiscount"
0x32ed  ldloc.1
0x32ee  ldstr    aTotaldiscount// "totaldiscount"
0x32f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32f8  unbox.any [mscorlib]System.Decimal
0x32fd  ldarg.0
0x32fe  ldloc.0
0x32ff  ldloc.1
0x3300  call     instance valuetype [mscorlib]System.Decimal Microsoft.Crm.Service.ObjectModel.ContractDetailService::ChangeDiscountToAmount(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity contractDetail, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity contract)
0x3305  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Subtraction(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x330a  box      [mscorlib]System.Decimal
0x330f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3314  ldloc.2
0x3315  ldstr    aNetprice// "netprice"
0x331a  ldloc.1
0x331b  ldstr    aNetprice// "netprice"
0x3320  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3325  unbox.any [mscorlib]System.Decimal
0x332a  ldloc.0
0x332b  ldstr    aNet// "net"
0x3330  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3335  unbox.any [mscorlib]System.Decimal
0x333a  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Subtraction(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x333f  box      [mscorlib]System.Decimal
0x3344  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3349  ldloc.2
0x334a  ldarg.s  4
0x334c  callvirt instance void Microsoft.Crm.Service.ObjectModel.ContractService::InternalUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3351  ldarg.1
0x3352  ldloc.0
0x3353  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3358  ldarg.s  4
0x335a  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x335f  stloc.3
0x3360  ldarg.0
0x3361  ldloc.3
0x3362  ldc.i4.2
0x3363  ldarg.2
0x3364  ldarg.s  4
0x3366  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x336b  ret
```
