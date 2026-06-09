# Microsoft.Crm.Service.ObjectModel.ContractService::Activate

- ea: `0x3960`
- end: `0x3a7c`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::Activate`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3710`

## callees

- `0x3960`
- `0x4220`

## pseudocode

```c

```

## disassembly

```asm
0x3960  ldnull
0x3961  stloc.0
0x3962  ldarg.3
0x3963  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3968  stloc.s  4
0x396a  ldarg.0
0x396b  ldarg.1
0x396c  ldarg.3
0x396d  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract Microsoft.Crm.Service.ObjectModel.ContractService::GetContract(valuetype [mscorlib]System.Guid contractId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3972  stloc.0
0x3973  leave.s  loc_3981
0x3975  ldloc.s  4
0x3977  brfalse.s loc_3980
0x3979  ldloc.s  4
0x397b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3980  endfinally
0x3981  ldloc.0
0x3982  ldstr    aStatecode// "statecode"
0x3987  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x398c  unbox.any [mscorlib]System.Int32
0x3991  ldc.i4.2
0x3992  bne.un.s loc_3996
0x3994  ldc.i4.1
0x3995  ret
0x3996  ldloc.0
0x3997  ldstr    aStatecode// "statecode"
0x399c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x39a1  unbox.any [mscorlib]System.Int32
0x39a6  ldc.i4.1
0x39a7  beq.s    loc_39BA
0x39a9  ldc.i4   0x80043203
0x39ae  ldc.i4.0
0x39af  newarr   [mscorlib]System.Object
0x39b4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x39b9  throw
0x39ba  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x39bf  stloc.1
0x39c0  ldloc.0
0x39c1  ldstr    aActiveon// "activeon"
0x39c6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x39cb  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x39d0  stloc.2
0x39d1  ldloc.0
0x39d2  ldstr    aExpireson// "expireson"
0x39d7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x39dc  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x39e1  stloc.3
0x39e2  ldloc.3
0x39e3  ldloc.2
0x39e4  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x39e9  stloc.s  5
0x39eb  ldloca.s 5
0x39ed  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x39f2  ldc.r8   0.0
0x39fb  bgt.un.s loc_3A0E
0x39fd  ldc.i4   0x80043202
0x3a02  ldc.i4.0
0x3a03  newarr   [mscorlib]System.Object
0x3a08  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3a0d  throw
0x3a0e  ldloc.1
0x3a0f  ldloc.2
0x3a10  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3a15  stloc.s  5
0x3a17  ldloca.s 5
0x3a19  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3a1e  ldc.r8   0.0
0x3a27  bge.un.s loc_3A3A
0x3a29  ldc.i4   0x80043202
0x3a2e  ldc.i4.0
0x3a2f  newarr   [mscorlib]System.Object
0x3a34  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3a39  throw
0x3a3a  ldloc.1
0x3a3b  ldloc.3
0x3a3c  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3a41  stloc.s  5
0x3a43  ldloca.s 5
0x3a45  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3a4a  ldc.r8   0.0
0x3a53  ble.un.s loc_3A66
0x3a55  ldc.i4   0x80043202
0x3a5a  ldc.i4.0
0x3a5b  newarr   [mscorlib]System.Object
0x3a60  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3a65  throw
0x3a66  ldarg.0
0x3a67  ldarg.1
0x3a68  ldstr    aContract// "Contract"
0x3a6d  ldarg.3
0x3a6e  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a73  ldc.i4.2
0x3a74  ldarg.2
0x3a75  ldarg.3
0x3a76  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3a7b  ret
```
