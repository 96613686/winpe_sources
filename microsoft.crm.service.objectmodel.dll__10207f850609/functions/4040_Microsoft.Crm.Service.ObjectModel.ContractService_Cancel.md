# Microsoft.Crm.Service.ObjectModel.ContractService::Cancel

- ea: `0x4040`
- end: `0x4215`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::Cancel`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x3710`

## callees

- `0x3150`
- `0x31c0`
- `0x36c0`
- `0x4040`
- `0x4220`
- `0x42d0`

## pseudocode

```c

```

## disassembly

```asm
0x4040  ldarg.2
0x4041  ldc.i4.1
0x4042  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x4047  stloc.0
0x4048  ldnull
0x4049  stloc.1
0x404a  ldarg.s  4
0x404c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4051  stloc.3
0x4052  ldarg.0
0x4053  ldarg.1
0x4054  ldarg.s  4
0x4056  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract Microsoft.Crm.Service.ObjectModel.ContractService::GetContract(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x405b  stloc.1
0x405c  leave.s  loc_4068
0x405e  ldloc.3
0x405f  brfalse.s loc_4067
0x4061  ldloc.3
0x4062  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4067  endfinally
0x4068  ldloc.1
0x4069  ldstr    aStatecode// "statecode"
0x406e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4073  unbox.any [mscorlib]System.Int32
0x4078  ldc.i4.4
0x4079  bne.un.s loc_407D
0x407b  ldc.i4.1
0x407c  ret
0x407d  ldloc.1
0x407e  ldstr    aStatecode// "statecode"
0x4083  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4088  unbox.any [mscorlib]System.Int32
0x408d  ldc.i4.1
0x408e  beq.s    loc_40B4
0x4090  ldloc.1
0x4091  ldstr    aStatecode// "statecode"
0x4096  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x409b  unbox.any [mscorlib]System.Int32
0x40a0  ldc.i4.2
0x40a1  beq.s    loc_40B4
0x40a3  ldc.i4   0x80043203
0x40a8  ldc.i4.0
0x40a9  newarr   [mscorlib]System.Object
0x40ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x40b3  throw
0x40b4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x40b9  stloc.2
0x40ba  ldloc.0
0x40bb  ldloc.2
0x40bc  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x40c1  stloc.s  4
0x40c3  ldloca.s 4
0x40c5  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x40ca  ldc.r8   0.0
0x40d3  bgt.un   loc_41DC
0x40d8  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractDetailService::.ctor()
0x40dd  stloc.s  5
0x40df  ldarg.0
0x40e0  ldloc.1
0x40e1  ldstr    aContractid// "contractid"
0x40e6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x40eb  unbox.any [mscorlib]System.Guid
0x40f0  ldarg.s  4
0x40f2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetails(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x40f7  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x40fc  stloc.s  7
0x40fe  br.s     loc_412B
0x4100  ldloc.s  7
0x4102  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4107  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x410c  stloc.s  8
0x410e  ldloc.s  5
0x4110  ldloc.s  8
0x4112  ldstr    aContractdetail// "contractdetailid"
0x4117  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x411c  unbox.any [mscorlib]System.Guid
0x4121  ldc.i4.m1
0x4122  ldc.i4.1
0x4123  ldarg.s  4
0x4125  callvirt instance bool Microsoft.Crm.Service.ObjectModel.ContractDetailService::Cancel(valuetype [mscorlib]System.Guid contractDetailId, int32 status, bool ignoreContractAndLineStatus, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x412a  pop
0x412b  ldloc.s  7
0x412d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4132  brtrue.s loc_4100
0x4134  leave.s  loc_414B
0x4136  ldloc.s  7
0x4138  isinst   [mscorlib]System.IDisposable
0x413d  stloc.s  9
0x413f  ldloc.s  9
0x4141  brfalse.s loc_414A
0x4143  ldloc.s  9
0x4145  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x414a  endfinally
0x414b  ldarg.s  4
0x414d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4152  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract::.ctor(valuetype [mscorlib]System.Guid)
0x4157  stloc.s  6
0x4159  ldloc.s  6
0x415b  ldstr    aContractid// "contractid"
0x4160  ldarg.1
0x4161  box      [mscorlib]System.Guid
0x4166  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x416b  ldloc.s  6
0x416d  ldstr    aCancelon// "cancelon"
0x4172  ldloc.0
0x4173  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4178  ldloc.s  6
0x417a  ldstr    aTotalprice// "totalprice"
0x417f  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Zero
0x4184  box      [mscorlib]System.Decimal
0x4189  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x418e  ldloc.s  6
0x4190  ldstr    aTotaldiscount// "totaldiscount"
0x4195  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Zero
0x419a  box      [mscorlib]System.Decimal
0x419f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x41a4  ldloc.s  6
0x41a6  ldstr    aNetprice// "netprice"
0x41ab  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Zero
0x41b0  box      [mscorlib]System.Decimal
0x41b5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x41ba  ldarg.0
0x41bb  ldloc.s  6
0x41bd  ldarg.s  4
0x41bf  call     instance void Microsoft.Crm.Service.ObjectModel.ContractService::InternalUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41c4  ldarg.0
0x41c5  ldarg.1
0x41c6  ldstr    aContract// "Contract"
0x41cb  ldarg.s  4
0x41cd  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41d2  ldc.i4.4
0x41d3  ldarg.3
0x41d4  ldarg.s  4
0x41d6  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41db  ret
0x41dc  ldarg.s  4
0x41de  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x41e3  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract::.ctor(valuetype [mscorlib]System.Guid)
0x41e8  stloc.s  0xA
0x41ea  ldloc.s  0xA
0x41ec  ldstr    aContractid// "contractid"
0x41f1  ldarg.1
0x41f2  box      [mscorlib]System.Guid
0x41f7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x41fc  ldloc.s  0xA
0x41fe  ldstr    aCancelon// "cancelon"
0x4203  ldloc.0
0x4204  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4209  ldarg.0
0x420a  ldloc.s  0xA
0x420c  ldarg.s  4
0x420e  call     instance void Microsoft.Crm.Service.ObjectModel.ContractService::InternalUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4213  ldc.i4.1
0x4214  ret
```
