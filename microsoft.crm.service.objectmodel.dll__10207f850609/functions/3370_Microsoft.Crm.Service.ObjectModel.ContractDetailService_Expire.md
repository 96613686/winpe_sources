# Microsoft.Crm.Service.ObjectModel.ContractDetailService::Expire

- ea: `0x3370`
- end: `0x33e6`
- name: `Microsoft.Crm.Service.ObjectModel.ContractDetailService::Expire`
- size: `118`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3180`
- `0x3830`
- `0x3a80`
- `0x3da0`

## callees

- `0x3370`
- `0x35a0`

## pseudocode

```c

```

## disassembly

```asm
0x3370  ldnull
0x3371  stloc.0
0x3372  ldarg.s  4
0x3374  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3379  stloc.2
0x337a  ldarg.0
0x337b  ldarg.1
0x337c  ldarg.s  4
0x337e  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.ContractDetail Microsoft.Crm.Service.ObjectModel.ContractDetailService::GetContractDetail(valuetype [mscorlib]System.Guid contractDetailId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3383  stloc.0
0x3384  leave.s  loc_3390
0x3386  ldloc.2
0x3387  brfalse.s loc_338F
0x3389  ldloc.2
0x338a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x338f  endfinally
0x3390  ldloc.0
0x3391  ldstr    aStatecode// "statecode"
0x3396  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x339b  unbox.any [mscorlib]System.Int32
0x33a0  ldc.i4.3
0x33a1  bne.un.s loc_33A5
0x33a3  ldc.i4.1
0x33a4  ret
0x33a5  ldarg.3
0x33a6  brtrue.s loc_33CB
0x33a8  ldloc.0
0x33a9  ldstr    aStatecode// "statecode"
0x33ae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x33b3  unbox.any [mscorlib]System.Int32
0x33b8  ldc.i4.2
0x33b9  bne.un.s loc_33CB
0x33bb  ldstr    aTheContractLin_1// "The contract line item cannot be expire"...
0x33c0  ldc.i4   0x80043204
0x33c5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x33ca  throw
0x33cb  ldarg.1
0x33cc  ldloc.0
0x33cd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x33d2  ldarg.s  4
0x33d4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x33d9  stloc.1
0x33da  ldarg.0
0x33db  ldloc.1
0x33dc  ldc.i4.3
0x33dd  ldarg.2
0x33de  ldarg.s  4
0x33e0  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x33e5  ret
```
