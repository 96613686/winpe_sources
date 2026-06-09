# Microsoft.Crm.Service.ObjectModel.ContractDetailService::ChangeDiscountToAmount

- ea: `0x33f0`
- end: `0x348c`
- name: `Microsoft.Crm.Service.ObjectModel.ContractDetailService::ChangeDiscountToAmount`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x31c0`
- `0x4520`

## callees

- `0x33f0`

## pseudocode

```c

```

## disassembly

```asm
0x33f0  ldloca.s 0
0x33f2  ldc.i4.0
0x33f3  ldc.i4.0
0x33f4  ldc.i4.0
0x33f5  ldc.i4.0
0x33f6  ldc.i4.1
0x33f7  call     instance void [mscorlib]System.Decimal::.ctor(int32, int32, int32, bool, unsigned int8)
0x33fc  ldarg.1
0x33fd  ldstr    aDiscount// "discount"
0x3402  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x3407  brtrue.s loc_341A
0x3409  ldarg.1
0x340a  ldstr    aDiscount// "discount"
0x340f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x3414  unbox.any [mscorlib]System.Decimal
0x3419  stloc.0
0x341a  ldloca.s 1
0x341c  ldc.i4.0
0x341d  ldc.i4.0
0x341e  ldc.i4.0
0x341f  ldc.i4.0
0x3420  ldc.i4.1
0x3421  call     instance void [mscorlib]System.Decimal::.ctor(int32, int32, int32, bool, unsigned int8)
0x3426  ldarg.1
0x3427  ldstr    aDiscountpercen// "discountpercentage"
0x342c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x3431  brtrue.s loc_3444
0x3433  ldarg.1
0x3434  ldstr    aDiscountpercen// "discountpercentage"
0x3439  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x343e  unbox.any [mscorlib]System.Decimal
0x3443  stloc.1
0x3444  ldc.i4.0
0x3445  stloc.2
0x3446  ldarg.2
0x3447  ldstr    aUsediscountasp// "usediscountaspercentage"
0x344c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x3451  brtrue.s loc_3464
0x3453  ldarg.2
0x3454  ldstr    aUsediscountasp// "usediscountaspercentage"
0x3459  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x345e  unbox.any [mscorlib]System.Boolean
0x3463  stloc.2
0x3464  ldloc.2
0x3465  brfalse.s loc_348A
0x3467  ldarg.1
0x3468  ldstr    aPrice// "price"
0x346d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x3472  unbox.any [mscorlib]System.Decimal
0x3477  ldloc.1
0x3478  ldc.i4.s 0x64
0x347a  newobj   instance void [mscorlib]System.Decimal::.ctor(int32)
0x347f  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Division(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x3484  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Multiply(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x3489  ret
0x348a  ldloc.0
0x348b  ret
```
