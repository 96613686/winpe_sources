# Microsoft.Crm.Transformations.AddToCurrentDate::Evaluate

- ea: `0x4d0`
- end: `0x7bd`
- name: `Microsoft.Crm.Transformations.AddToCurrentDate::Evaluate`
- size: `749`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x4d0`
- `0x7c0`

## pseudocode

```c

```

## disassembly

```asm
0x4d0  ldarg.1
0x4d1  brfalse.s loc_4D9
0x4d3  ldarg.1
0x4d4  ldlen
0x4d5  conv.i4
0x4d6  ldc.i4.7
0x4d7  beq.s    loc_4EA
0x4d9  ldc.i4   0x80048506
0x4de  ldc.i4.0
0x4df  newarr   [mscorlib]System.Object
0x4e4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x4e9  throw
0x4ea  ldarg.0
0x4eb  ldarg.1
0x4ec  call     instance void Microsoft.Crm.Transformations.AddToCurrentDate::PerformParameterValidations(object[] input)
0x4f1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4f6  stloc.0
0x4f7  ldc.i4.0
0x4f8  stloc.1
0x4f9  ldloca.s 0
0x4fb  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x500  stloc.2
0x501  ldc.i4.0
0x502  stloc.3
0x503  ldloca.s 0
0x505  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x50a  stloc.s  4
0x50c  ldc.i4.0
0x50d  stloc.s  5
0x50f  ldloca.s 0
0x511  call     instance int32 [mscorlib]System.DateTime::get_Day()
0x516  stloc.s  6
0x518  ldloca.s 0
0x51a  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x51f  stloc.s  7
0x521  ldloca.s 0
0x523  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0x528  stloc.s  8
0x52a  ldloca.s 0
0x52c  call     instance int32 [mscorlib]System.DateTime::get_Second()
0x531  stloc.s  9
0x533  ldc.i4.m1
0x534  stloc.s  0xA
0x536  ldarg.1
0x537  ldc.i4.0
0x538  ldelem.ref
0x539  brfalse.s loc_544
0x53b  ldarg.1
0x53c  ldc.i4.0
0x53d  ldelem.ref
0x53e  unbox.any [mscorlib]System.Int32
0x543  stloc.1
0x544  ldarg.1
0x545  ldc.i4.1
0x546  ldelem.ref
0x547  brfalse.s loc_552
0x549  ldarg.1
0x54a  ldc.i4.1
0x54b  ldelem.ref
0x54c  unbox.any [mscorlib]System.Int32
0x551  stloc.3
0x552  ldarg.1
0x553  ldc.i4.2
0x554  ldelem.ref
0x555  brfalse.s loc_561
0x557  ldarg.1
0x558  ldc.i4.2
0x559  ldelem.ref
0x55a  unbox.any [mscorlib]System.Int32
0x55f  stloc.s  5
0x561  ldarg.1
0x562  ldc.i4.3
0x563  ldelem.ref
0x564  brfalse.s loc_570
0x566  ldarg.1
0x567  ldc.i4.3
0x568  ldelem.ref
0x569  unbox.any [mscorlib]System.Int32
0x56e  stloc.s  7
0x570  ldarg.1
0x571  ldc.i4.4
0x572  ldelem.ref
0x573  brfalse.s loc_57F
0x575  ldarg.1
0x576  ldc.i4.4
0x577  ldelem.ref
0x578  unbox.any [mscorlib]System.Int32
0x57d  stloc.s  8
0x57f  ldarg.1
0x580  ldc.i4.5
0x581  ldelem.ref
0x582  brfalse.s loc_58E
0x584  ldarg.1
0x585  ldc.i4.5
0x586  ldelem.ref
0x587  unbox.any [mscorlib]System.Int32
0x58c  stloc.s  9
0x58e  ldarg.1
0x58f  ldc.i4.6
0x590  ldelem.ref
0x591  brfalse.s loc_59D
0x593  ldarg.1
0x594  ldc.i4.6
0x595  ldelem.ref
0x596  unbox.any [mscorlib]System.Int32
0x59b  stloc.s  0xA
0x59d  ldloc.s  0xA
0x59f  ldc.i4.m1
0x5a0  beq.s    loc_5E8
0x5a2  ldloc.s  0xA
0x5a4  ldc.i4.0
0x5a5  blt.s    loc_5AC
0x5a7  ldloc.s  0xA
0x5a9  ldc.i4.6
0x5aa  ble.s    loc_5E8
0x5ac  ldc.i4   0x80048510
0x5b1  ldc.i4.3
0x5b2  newarr   [mscorlib]System.Object
0x5b7  dup
0x5b8  ldc.i4.0
0x5b9  ldstr    a7// "7"
0x5be  stelem.ref
0x5bf  dup
0x5c0  ldc.i4.1
0x5c1  ldloc.s  0xA
0x5c3  box      [mscorlib]System.Int32
0x5c8  stelem.ref
0x5c9  dup
0x5ca  ldc.i4.2
0x5cb  ldc.i4.m1
0x5cc  box      [mscorlib]System.Int32
0x5d1  ldstr    asc_3EE2// " - "
0x5d6  ldc.i4.6
0x5d7  box      [mscorlib]System.Int32
0x5dc  call     string [mscorlib]System.String::Concat(object, object, object)
0x5e1  stelem.ref
0x5e2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x5e7  throw
0x5e8  nop
0x5e9  ldloc.2
0x5ea  ldloc.s  4
0x5ec  ldloc.s  6
0x5ee  ldloc.s  7
0x5f0  ldloc.s  8
0x5f2  ldloc.s  9
0x5f4  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32)
0x5f9  stloc.s  0xB
0x5fb  leave    loc_6D8
0x600  stloc.s  0xC
0x602  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x607  ldstr    aYear0Month1Day// "Year: {0}, Month: {1}, Day: {2}, Hours:"...
0x60c  ldc.i4.6
0x60d  newarr   [mscorlib]System.Object
0x612  dup
0x613  ldc.i4.0
0x614  ldloc.2
0x615  box      [mscorlib]System.Int32
0x61a  stelem.ref
0x61b  dup
0x61c  ldc.i4.1
0x61d  ldloc.s  4
0x61f  box      [mscorlib]System.Int32
0x624  stelem.ref
0x625  dup
0x626  ldc.i4.2
0x627  ldloc.s  6
0x629  box      [mscorlib]System.Int32
0x62e  stelem.ref
0x62f  dup
0x630  ldc.i4.3
0x631  ldloc.s  7
0x633  box      [mscorlib]System.Int32
0x638  stelem.ref
0x639  dup
0x63a  ldc.i4.4
0x63b  ldloc.s  8
0x63d  box      [mscorlib]System.Int32
0x642  stelem.ref
0x643  dup
0x644  ldc.i4.5
0x645  ldloc.s  9
0x647  box      [mscorlib]System.Int32
0x64c  stelem.ref
0x64d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x652  stloc.s  0xD
0x654  ldloc.s  0xC
0x656  ldc.i4   0x80048512
0x65b  ldc.i4.1
0x65c  newarr   [mscorlib]System.Object
0x661  dup
0x662  ldc.i4.0
0x663  ldloc.s  0xD
0x665  stelem.ref
0x666  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, object[])
0x66b  throw
0x66c  stloc.s  0xE
0x66e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x673  ldstr    aYear0Month1Day// "Year: {0}, Month: {1}, Day: {2}, Hours:"...
0x678  ldc.i4.6
0x679  newarr   [mscorlib]System.Object
0x67e  dup
0x67f  ldc.i4.0
0x680  ldloc.2
0x681  box      [mscorlib]System.Int32
0x686  stelem.ref
0x687  dup
0x688  ldc.i4.1
0x689  ldloc.s  4
0x68b  box      [mscorlib]System.Int32
0x690  stelem.ref
0x691  dup
0x692  ldc.i4.2
0x693  ldloc.s  6
0x695  box      [mscorlib]System.Int32
0x69a  stelem.ref
0x69b  dup
0x69c  ldc.i4.3
0x69d  ldloc.s  7
0x69f  box      [mscorlib]System.Int32
0x6a4  stelem.ref
0x6a5  dup
0x6a6  ldc.i4.4
0x6a7  ldloc.s  8
0x6a9  box      [mscorlib]System.Int32
0x6ae  stelem.ref
0x6af  dup
0x6b0  ldc.i4.5
0x6b1  ldloc.s  9
0x6b3  box      [mscorlib]System.Int32
0x6b8  stelem.ref
0x6b9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6be  stloc.s  0xF
0x6c0  ldloc.s  0xE
0x6c2  ldc.i4   0x80048513
0x6c7  ldc.i4.1
0x6c8  newarr   [mscorlib]System.Object
0x6cd  dup
0x6ce  ldc.i4.0
0x6cf  ldloc.s  0xF
0x6d1  stelem.ref
0x6d2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, object[])
0x6d7  throw
0x6d8  nop
0x6d9  ldloca.s 0xB
0x6db  ldloc.s  5
0x6dd  conv.r8
0x6de  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x6e3  stloc.s  0xB
0x6e5  leave.s  loc_710
0x6e7  stloc.s  0x10
0x6e9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6ee  ldstr    aAdding0DaysToT// "Adding {0} days to the date threw excep"...
0x6f3  ldc.i4.1
0x6f4  newarr   [mscorlib]System.Object
0x6f9  dup
0x6fa  ldc.i4.0
0x6fb  ldloc.s  5
0x6fd  box      [mscorlib]System.Int32
0x702  stelem.ref
0x703  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x708  ldloc.s  0x10
0x70a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InvalidTransformationExecutionException::.ctor(string, class [mscorlib]System.Exception)
0x70f  throw
0x710  nop
0x711  ldloca.s 0xB
0x713  ldloc.3
0x714  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMonths(int32)
0x719  stloc.s  0xB
0x71b  leave.s  loc_745
0x71d  stloc.s  0x11
0x71f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x724  ldstr    aAdding0MonthsT// "Adding {0} months to the date threw exc"...
0x729  ldc.i4.1
0x72a  newarr   [mscorlib]System.Object
0x72f  dup
0x730  ldc.i4.0
0x731  ldloc.3
0x732  box      [mscorlib]System.Int32
0x737  stelem.ref
0x738  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x73d  ldloc.s  0x11
0x73f  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InvalidTransformationExecutionException::.ctor(string, class [mscorlib]System.Exception)
0x744  throw
0x745  nop
0x746  ldloca.s 0xB
0x748  ldloc.1
0x749  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddYears(int32)
0x74e  stloc.s  0xB
0x750  leave.s  loc_77A
0x752  stloc.s  0x12
0x754  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x759  ldstr    aAdding0YearsTo// "Adding {0} years to the date threw exce"...
0x75e  ldc.i4.1
0x75f  newarr   [mscorlib]System.Object
0x764  dup
0x765  ldc.i4.0
0x766  ldloc.1
0x767  box      [mscorlib]System.Int32
0x76c  stelem.ref
0x76d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
  ... truncated ...
```
