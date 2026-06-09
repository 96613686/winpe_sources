# Microsoft.Crm.Transformations.AddToDate::Evaluate

- ea: `0xd90`
- end: `0x109e`
- name: `Microsoft.Crm.Transformations.AddToDate::Evaluate`
- size: `782`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xd90`

## pseudocode

```c

```

## disassembly

```asm
0xd90  ldarg.1
0xd91  brfalse.s loc_D99
0xd93  ldarg.1
0xd94  ldlen
0xd95  conv.i4
0xd96  ldc.i4.6
0xd97  beq.s    loc_DAA
0xd99  ldc.i4   0x80048506
0xd9e  ldc.i4.0
0xd9f  newarr   [mscorlib]System.Object
0xda4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xda9  throw
0xdaa  ldarg.1
0xdab  ldc.i4.0
0xdac  ldelem.ref
0xdad  brtrue.s loc_DB6
0xdaf  ldc.i4.1
0xdb0  newarr   [mscorlib]System.Object
0xdb5  ret
0xdb6  ldarg.1
0xdb7  ldc.i4.0
0xdb8  ldelem.ref
0xdb9  isinst   [mscorlib]System.DateTime
0xdbe  brtrue.s loc_DE7
0xdc0  ldc.i4   0x80048507
0xdc5  ldc.i4.3
0xdc6  newarr   [mscorlib]System.Object
0xdcb  dup
0xdcc  ldc.i4.0
0xdcd  ldstr    a1// "1"
0xdd2  stelem.ref
0xdd3  dup
0xdd4  ldc.i4.1
0xdd5  ldarg.1
0xdd6  ldc.i4.0
0xdd7  ldelem.ref
0xdd8  stelem.ref
0xdd9  dup
0xdda  ldc.i4.2
0xddb  ldstr    aDatetime// "DateTime"
0xde0  stelem.ref
0xde1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xde6  throw
0xde7  ldarg.1
0xde8  ldc.i4.0
0xde9  ldelem.ref
0xdea  unbox.any [mscorlib]System.DateTime
0xdef  stloc.0
0xdf0  ldc.i4.0
0xdf1  stloc.1
0xdf2  ldc.i4.0
0xdf3  stloc.2
0xdf4  ldc.i4.0
0xdf5  stloc.3
0xdf6  ldloca.s 0
0xdf8  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xdfd  stloc.s  4
0xdff  ldc.i4.0
0xe00  stloc.s  5
0xe02  ldarg.1
0xe03  ldc.i4.1
0xe04  ldelem.ref
0xe05  brfalse.s loc_E38
0xe07  ldarg.1
0xe08  ldc.i4.1
0xe09  ldelem.ref
0xe0a  isinst   [mscorlib]System.Int32
0xe0f  brtrue.s loc_E38
0xe11  ldc.i4   0x80048507
0xe16  ldc.i4.3
0xe17  newarr   [mscorlib]System.Object
0xe1c  dup
0xe1d  ldc.i4.0
0xe1e  ldstr    a2// "2"
0xe23  stelem.ref
0xe24  dup
0xe25  ldc.i4.1
0xe26  ldarg.1
0xe27  ldc.i4.1
0xe28  ldelem.ref
0xe29  stelem.ref
0xe2a  dup
0xe2b  ldc.i4.2
0xe2c  ldstr    aInteger// "Integer"
0xe31  stelem.ref
0xe32  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xe37  throw
0xe38  ldarg.1
0xe39  ldc.i4.2
0xe3a  ldelem.ref
0xe3b  brfalse.s loc_E6E
0xe3d  ldarg.1
0xe3e  ldc.i4.2
0xe3f  ldelem.ref
0xe40  isinst   [mscorlib]System.Int32
0xe45  brtrue.s loc_E6E
0xe47  ldc.i4   0x80048507
0xe4c  ldc.i4.3
0xe4d  newarr   [mscorlib]System.Object
0xe52  dup
0xe53  ldc.i4.0
0xe54  ldstr    a3// "3"
0xe59  stelem.ref
0xe5a  dup
0xe5b  ldc.i4.1
0xe5c  ldarg.1
0xe5d  ldc.i4.1
0xe5e  ldelem.ref
0xe5f  stelem.ref
0xe60  dup
0xe61  ldc.i4.2
0xe62  ldstr    aInteger// "Integer"
0xe67  stelem.ref
0xe68  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xe6d  throw
0xe6e  ldarg.1
0xe6f  ldc.i4.3
0xe70  ldelem.ref
0xe71  brfalse.s loc_EA4
0xe73  ldarg.1
0xe74  ldc.i4.3
0xe75  ldelem.ref
0xe76  isinst   [mscorlib]System.Int32
0xe7b  brtrue.s loc_EA4
0xe7d  ldc.i4   0x80048507
0xe82  ldc.i4.3
0xe83  newarr   [mscorlib]System.Object
0xe88  dup
0xe89  ldc.i4.0
0xe8a  ldstr    a4// "4"
0xe8f  stelem.ref
0xe90  dup
0xe91  ldc.i4.1
0xe92  ldarg.1
0xe93  ldc.i4.1
0xe94  ldelem.ref
0xe95  stelem.ref
0xe96  dup
0xe97  ldc.i4.2
0xe98  ldstr    aInteger// "Integer"
0xe9d  stelem.ref
0xe9e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xea3  throw
0xea4  ldarg.1
0xea5  ldc.i4.4
0xea6  ldelem.ref
0xea7  brfalse.s loc_EDA
0xea9  ldarg.1
0xeaa  ldc.i4.4
0xeab  ldelem.ref
0xeac  isinst   [mscorlib]System.DateTime
0xeb1  brtrue.s loc_EDA
0xeb3  ldc.i4   0x80048507
0xeb8  ldc.i4.3
0xeb9  newarr   [mscorlib]System.Object
0xebe  dup
0xebf  ldc.i4.0
0xec0  ldstr    a5// "5"
0xec5  stelem.ref
0xec6  dup
0xec7  ldc.i4.1
0xec8  ldarg.1
0xec9  ldc.i4.1
0xeca  ldelem.ref
0xecb  stelem.ref
0xecc  dup
0xecd  ldc.i4.2
0xece  ldstr    aDatetime// "DateTime"
0xed3  stelem.ref
0xed4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xed9  throw
0xeda  ldarg.1
0xedb  ldc.i4.5
0xedc  ldelem.ref
0xedd  brfalse.s loc_F10
0xedf  ldarg.1
0xee0  ldc.i4.5
0xee1  ldelem.ref
0xee2  isinst   [mscorlib]System.Int32
0xee7  brtrue.s loc_F10
0xee9  ldc.i4   0x80048507
0xeee  ldc.i4.3
0xeef  newarr   [mscorlib]System.Object
0xef4  dup
0xef5  ldc.i4.0
0xef6  ldstr    a6// "6"
0xefb  stelem.ref
0xefc  dup
0xefd  ldc.i4.1
0xefe  ldarg.1
0xeff  ldc.i4.1
0xf00  ldelem.ref
0xf01  stelem.ref
0xf02  dup
0xf03  ldc.i4.2
0xf04  ldstr    aInteger// "Integer"
0xf09  stelem.ref
0xf0a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xf0f  throw
0xf10  ldarg.1
0xf11  ldc.i4.1
0xf12  ldelem.ref
0xf13  brfalse.s loc_F1E
0xf15  ldarg.1
0xf16  ldc.i4.1
0xf17  ldelem.ref
0xf18  unbox.any [mscorlib]System.Int32
0xf1d  stloc.1
0xf1e  ldarg.1
0xf1f  ldc.i4.2
0xf20  ldelem.ref
0xf21  brfalse.s loc_F2C
0xf23  ldarg.1
0xf24  ldc.i4.2
0xf25  ldelem.ref
0xf26  unbox.any [mscorlib]System.Int32
0xf2b  stloc.2
0xf2c  ldarg.1
0xf2d  ldc.i4.3
0xf2e  ldelem.ref
0xf2f  brfalse.s loc_F3A
0xf31  ldarg.1
0xf32  ldc.i4.3
0xf33  ldelem.ref
0xf34  unbox.any [mscorlib]System.Int32
0xf39  stloc.3
0xf3a  ldarg.1
0xf3b  ldc.i4.4
0xf3c  ldelem.ref
0xf3d  brfalse.s loc_F49
0xf3f  ldarg.1
0xf40  ldc.i4.4
0xf41  ldelem.ref
0xf42  unbox.any [mscorlib]System.DateTime
0xf47  stloc.s  4
0xf49  ldarg.1
0xf4a  ldc.i4.5
0xf4b  ldelem.ref
0xf4c  brfalse.s loc_F58
0xf4e  ldarg.1
0xf4f  ldc.i4.5
0xf50  ldelem.ref
0xf51  unbox.any [mscorlib]System.Int32
0xf56  stloc.s  5
0xf58  nop
0xf59  ldloca.s 0
0xf5b  ldloc.3
0xf5c  conv.r8
0xf5d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xf62  stloc.s  6
0xf64  leave.s  loc_F8E
0xf66  stloc.s  7
0xf68  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf6d  ldstr    aAdding0DaysToT// "Adding {0} days to the date threw excep"...
0xf72  ldc.i4.1
0xf73  newarr   [mscorlib]System.Object
0xf78  dup
0xf79  ldc.i4.0
0xf7a  ldloc.3
0xf7b  box      [mscorlib]System.Int32
0xf80  stelem.ref
0xf81  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf86  ldloc.s  7
0xf88  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InvalidTransformationExecutionException::.ctor(string, class [mscorlib]System.Exception)
0xf8d  throw
0xf8e  nop
0xf8f  ldloca.s 6
0xf91  ldloc.2
0xf92  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMonths(int32)
0xf97  stloc.s  6
0xf99  leave.s  loc_FC3
0xf9b  stloc.s  8
0xf9d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfa2  ldstr    aAdding0MonthsT// "Adding {0} months to the date threw exc"...
0xfa7  ldc.i4.1
0xfa8  newarr   [mscorlib]System.Object
0xfad  dup
0xfae  ldc.i4.0
0xfaf  ldloc.2
0xfb0  box      [mscorlib]System.Int32
0xfb5  stelem.ref
0xfb6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xfbb  ldloc.s  8
0xfbd  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InvalidTransformationExecutionException::.ctor(string, class [mscorlib]System.Exception)
0xfc2  throw
0xfc3  nop
0xfc4  ldloca.s 6
0xfc6  ldloc.1
0xfc7  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddYears(int32)
0xfcc  stloc.s  6
0xfce  leave.s  loc_FF8
0xfd0  stloc.s  9
0xfd2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfd7  ldstr    aAdding0YearsTo// "Adding {0} years to the date threw exce"...
0xfdc  ldc.i4.1
0xfdd  newarr   [mscorlib]System.Object
0xfe2  dup
0xfe3  ldc.i4.0
0xfe4  ldloc.1
0xfe5  box      [mscorlib]System.Int32
  ... truncated ...
```
