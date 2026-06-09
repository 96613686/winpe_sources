# Microsoft.Crm.Service.ObjectModel.ContractService::UpdateCalculatedFields

- ea: `0x4520`
- end: `0x4663`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::UpdateCalculatedFields`
- size: `323`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x3150`
- `0x33f0`
- `0x42e0`
- `0x4520`

## pseudocode

```c

```

## disassembly

```asm
0x4520  ldloca.s 0
0x4522  initobj  [mscorlib]System.Decimal
0x4528  ldloca.s 1
0x452a  initobj  [mscorlib]System.Decimal
0x4530  ldloca.s 2
0x4532  initobj  [mscorlib]System.Decimal
0x4538  ldloca.s 3
0x453a  initobj  [mscorlib]System.Decimal
0x4540  ldloca.s 4
0x4542  initobj  [mscorlib]System.Decimal
0x4548  ldloca.s 5
0x454a  initobj  [mscorlib]System.Decimal
0x4550  ldc.i4.4
0x4551  newarr   [mscorlib]System.String
0x4556  dup
0x4557  ldc.i4.0
0x4558  ldstr    aPrice// "price"
0x455d  stelem.ref
0x455e  dup
0x455f  ldc.i4.1
0x4560  ldstr    aDiscount// "discount"
0x4565  stelem.ref
0x4566  dup
0x4567  ldc.i4.2
0x4568  ldstr    aDiscountpercen// "discountpercentage"
0x456d  stelem.ref
0x456e  dup
0x456f  ldc.i4.3
0x4570  ldstr    aNet// "net"
0x4575  stelem.ref
0x4576  stloc.s  6
0x4578  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::.ctor()
0x457d  stloc.s  7
0x457f  ldarg.0
0x4580  ldarg.1
0x4581  ldstr    aContractid// "contractid"
0x4586  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x458b  unbox.any [mscorlib]System.Guid
0x4590  ldloc.s  6
0x4592  ldc.i4.0
0x4593  ldarg.2
0x4594  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetails(valuetype [mscorlib]System.Guid contractId, string[] columns, bool allColumns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4599  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x459e  stloc.s  8
0x45a0  br.s     loc_460F
0x45a2  ldloc.s  8
0x45a4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x45a9  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x45ae  stloc.s  9
0x45b0  ldloc.s  9
0x45b2  ldstr    aPrice// "price"
0x45b7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x45bc  unbox.any [mscorlib]System.Decimal
0x45c1  stloc.3
0x45c2  ldloc.s  9
0x45c4  ldstr    aNet// "net"
0x45c9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x45ce  unbox.any [mscorlib]System.Decimal
0x45d3  stloc.s  5
0x45d5  ldloc.s  7
0x45d7  ldloc.s  9
0x45d9  ldarg.1
0x45da  callvirt instance valuetype [mscorlib]System.Decimal Microsoft.Crm.Service.ObjectModel.ContractDetailService::ChangeDiscountToAmount(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity contractDetail, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity contract)
0x45df  stloc.s  4
0x45e1  ldloc.3
0x45e2  ldloc.s  4
0x45e4  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Subtraction(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x45e9  stloc.s  5
0x45eb  ldloc.s  7
0x45ed  ldloc.s  9
0x45ef  ldarg.2
0x45f0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x45f5  ldloc.0
0x45f6  ldloc.3
0x45f7  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Addition(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x45fc  stloc.0
0x45fd  ldloc.1
0x45fe  ldloc.s  4
0x4600  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Addition(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x4605  stloc.1
0x4606  ldloc.2
0x4607  ldloc.s  5
0x4609  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Addition(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x460e  stloc.2
0x460f  ldloc.s  8
0x4611  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4616  brtrue.s loc_45A2
0x4618  leave.s  loc_462F
0x461a  ldloc.s  8
0x461c  isinst   [mscorlib]System.IDisposable
0x4621  stloc.s  0xA
0x4623  ldloc.s  0xA
0x4625  brfalse.s loc_462E
0x4627  ldloc.s  0xA
0x4629  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x462e  endfinally
0x462f  ldarg.1
0x4630  ldstr    aTotalprice// "totalprice"
0x4635  ldloc.0
0x4636  box      [mscorlib]System.Decimal
0x463b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4640  ldarg.1
0x4641  ldstr    aTotaldiscount// "totaldiscount"
0x4646  ldloc.1
0x4647  box      [mscorlib]System.Decimal
0x464c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4651  ldarg.1
0x4652  ldstr    aNetprice// "netprice"
0x4657  ldloc.2
0x4658  box      [mscorlib]System.Decimal
0x465d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4662  ret
```
