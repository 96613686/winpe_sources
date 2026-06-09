# Microsoft.Crm.Service.ObjectModel.ContractService::SetState

- ea: `0x3710`
- end: `0x37da`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::SetState`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x3710`
- `0x3830`
- `0x3960`
- `0x3a80`
- `0x3d30`
- `0x3da0`
- `0x4040`
- `0x4220`
- `0x4740`

## pseudocode

```c

```

## disassembly

```asm
0x3710  ldarg.0
0x3711  ldarg.1
0x3712  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x3717  ldarg.s  4
0x3719  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract Microsoft.Crm.Service.ObjectModel.ContractService::GetContract(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x371e  ldstr    aStatecode// "statecode"
0x3723  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3728  unbox.any [mscorlib]System.Int32
0x372d  stloc.0
0x372e  ldc.i4.0
0x372f  stloc.1
0x3730  ldloc.0
0x3731  ldarg.2
0x3732  bne.un.s loc_3736
0x3734  ldc.i4.1
0x3735  ret
0x3736  ldarg.2
0x3737  ldc.i4.1
0x3738  sub
0x3739  switch   loc_3765, loc_37B4, loc_3754, loc_378B, loc_37A2
0x3752  br.s     loc_37C6
0x3754  ldarg.0
0x3755  ldarg.1
0x3756  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x375b  ldarg.s  4
0x375d  call     instance bool Microsoft.Crm.Service.ObjectModel.ContractService::Hold(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3762  stloc.1
0x3763  br.s     loc_37D1
0x3765  ldloc.0
0x3766  ldc.i4.3
0x3767  bne.un.s loc_377A
0x3769  ldarg.0
0x376a  ldarg.1
0x376b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x3770  ldarg.s  4
0x3772  call     instance bool Microsoft.Crm.Service.ObjectModel.ContractService::ReleaseHold(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3777  stloc.1
0x3778  br.s     loc_37D1
0x377a  ldarg.0
0x377b  ldarg.1
0x377c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x3781  ldarg.s  4
0x3783  call     instance bool Microsoft.Crm.Service.ObjectModel.ContractService::Invoice(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3788  stloc.1
0x3789  br.s     loc_37D1
0x378b  ldarg.0
0x378c  ldarg.1
0x378d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x3792  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3797  ldarg.3
0x3798  ldarg.s  4
0x379a  call     instance bool Microsoft.Crm.Service.ObjectModel.ContractService::Cancel(valuetype [mscorlib]System.Guid contractId, valuetype [mscorlib]System.DateTime cancelDate, int32 status, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x379f  stloc.1
0x37a0  br.s     loc_37D1
0x37a2  ldarg.0
0x37a3  ldarg.1
0x37a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x37a9  ldarg.3
0x37aa  ldarg.s  4
0x37ac  call     instance bool Microsoft.Crm.Service.ObjectModel.ContractService::Expire(valuetype [mscorlib]System.Guid contractId, int32 status, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x37b1  stloc.1
0x37b2  br.s     loc_37D1
0x37b4  ldarg.0
0x37b5  ldarg.1
0x37b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x37bb  ldarg.3
0x37bc  ldarg.s  4
0x37be  call     instance bool Microsoft.Crm.Service.ObjectModel.ContractService::Activate(valuetype [mscorlib]System.Guid contractId, int32 status, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x37c3  stloc.1
0x37c4  br.s     loc_37D1
0x37c6  ldstr    aTheTargetState// "The target state is invalid.  The targe"...
0x37cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x37d0  throw
0x37d1  ldarg.s  4
0x37d3  call     void Microsoft.Crm.Service.ObjectModel.ContractStateAsyncJobHelper::UpdateAsyncJobPostponeUntil(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x37d8  ldloc.1
0x37d9  ret
```
