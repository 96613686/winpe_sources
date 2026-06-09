# Microsoft.Crm.Service.ObjectModel.RuleServiceBase::InternalSetState

- ea: `0x8bb0`
- end: `0x8c14`
- name: `Microsoft.Crm.Service.ObjectModel.RuleServiceBase::InternalSetState`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x5210`
- `0x5680`

## callees

- `0x8bb0`
- `0x8db0`
- `0x90d0`

## pseudocode

```c

```

## disassembly

```asm
0x8bb0  ldarg.0
0x8bb1  ldarg.1
0x8bb2  ldarg.s  5
0x8bb4  call     instance void Microsoft.Crm.Service.ObjectModel.RuleServiceBase::CheckForOwnerOfRuleEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8bb9  ldarg.2
0x8bba  ldc.i4.1
0x8bbb  bne.un.s loc_8BE2
0x8bbd  ldarg.s  4
0x8bbf  ldstr    aStatecode// "statecode"
0x8bc4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8bc9  unbox.any [mscorlib]System.Int32
0x8bce  ldc.i4.1
0x8bcf  bne.un.s loc_8C06
0x8bd1  ldc.i4   0x8004F852
0x8bd6  ldc.i4.0
0x8bd7  newarr   [mscorlib]System.Object
0x8bdc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x8be1  throw
0x8be2  ldarg.s  4
0x8be4  ldstr    aStatecode// "statecode"
0x8be9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8bee  unbox.any [mscorlib]System.Int32
0x8bf3  brtrue.s loc_8C06
0x8bf5  ldc.i4   0x8004F853
0x8bfa  ldc.i4.0
0x8bfb  newarr   [mscorlib]System.Object
0x8c00  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x8c05  throw
0x8c06  ldarg.0
0x8c07  ldarg.1
0x8c08  ldarg.2
0x8c09  ldarg.3
0x8c0a  ldarg.s  4
0x8c0c  ldarg.s  5
0x8c0e  call     instance bool Microsoft.Crm.Service.ObjectModel.RuleServiceBase::SetStateRuleAndWorkflow(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity originalEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8c13  ret
```
