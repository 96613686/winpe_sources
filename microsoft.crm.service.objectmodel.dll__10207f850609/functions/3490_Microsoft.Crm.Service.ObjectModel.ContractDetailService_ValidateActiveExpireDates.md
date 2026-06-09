# Microsoft.Crm.Service.ObjectModel.ContractDetailService::ValidateActiveExpireDates

- ea: `0x3490`
- end: `0x359a`
- name: `Microsoft.Crm.Service.ObjectModel.ContractDetailService::ValidateActiveExpireDates`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a80`

## callees

- `0x3490`

## pseudocode

```c

```

## disassembly

```asm
0x3490  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::.ctor()
0x3495  pop
0x3496  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::.ctor()
0x349b  stloc.0
0x349c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::.ctor()
0x34a1  stloc.1
0x34a2  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::.ctor()
0x34a7  stloc.2
0x34a8  ldc.i4.0
0x34a9  stloc.3
0x34aa  ldc.i4.0
0x34ab  stloc.s  4
0x34ad  ldarg.1
0x34ae  ldstr    aActiveon// "activeon"
0x34b3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x34b8  brtrue.s loc_34FF
0x34ba  ldc.i4.1
0x34bb  stloc.3
0x34bc  ldarg.1
0x34bd  ldstr    aActiveon// "activeon"
0x34c2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x34c7  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x34cc  ldarg.2
0x34cd  ldstr    aActiveon// "activeon"
0x34d2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x34d7  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x34dc  stloc.0
0x34dd  ldloc.0
0x34de  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x34e3  stloc.s  5
0x34e5  ldloca.s 5
0x34e7  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x34ec  ldc.i4.0
0x34ed  bge.s    loc_34FF
0x34ef  ldstr    aTheStartDateIs// "The start date is invalid."
0x34f4  ldc.i4   0x80043202
0x34f9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x34fe  throw
0x34ff  ldarg.1
0x3500  ldstr    aExpireson// "expireson"
0x3505  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x350a  brtrue.s loc_3554
0x350c  ldc.i4.1
0x350d  stloc.s  4
0x350f  ldarg.1
0x3510  ldstr    aExpireson// "expireson"
0x3515  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x351a  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x351f  stloc.1
0x3520  ldarg.2
0x3521  ldstr    aExpireson// "expireson"
0x3526  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x352b  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x3530  stloc.2
0x3531  ldloc.2
0x3532  ldloc.1
0x3533  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x3538  stloc.s  5
0x353a  ldloca.s 5
0x353c  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x3541  ldc.i4.0
0x3542  bge.s    loc_3554
0x3544  ldstr    aTheEndDateIsIn// "The end date is invalid."
0x3549  ldc.i4   0x80043202
0x354e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3553  throw
0x3554  ldarg.3
0x3555  brfalse.s loc_356E
0x3557  ldloc.3
0x3558  brfalse.s loc_355E
0x355a  ldloc.s  4
0x355c  brtrue.s loc_356E
0x355e  ldstr    aTheStartDateEn// "The start date / end date is missing."
0x3563  ldc.i4   0x80043202
0x3568  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x356d  throw
0x356e  ldloc.3
0x356f  ldloc.s  4
0x3571  and
0x3572  brfalse.s loc_3599
0x3574  ldloc.2
0x3575  ldloc.0
0x3576  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::Subtract(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime)
0x357b  stloc.s  5
0x357d  ldloca.s 5
0x357f  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x3584  ldc.i4.1
0x3585  add
0x3586  ldc.i4.0
0x3587  bgt.s    loc_3599
0x3589  ldstr    aTheStartDateEn_0// "The start date / end date is invalid."
0x358e  ldc.i4   0x80043202
0x3593  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3598  throw
0x3599  ret
```
