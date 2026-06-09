# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetRelativeDate

- ea: `0x16f0`
- end: `0x179a`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetRelativeDate`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1300`

## callees

- `0x16f0`

## pseudocode

```c

```

## disassembly

```asm
0x16f0  ldarg.1
0x16f1  stloc.0
0x16f2  ldarg.3
0x16f3  ldc.i4.1
0x16f4  bne.un.s loc_1728
0x16f6  ldloca.s 0
0x16f8  ldarg.2
0x16f9  conv.r8
0x16fa  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x16ff  stloc.0
0x1700  leave.s  loc_1728
0x1702  stloc.1
0x1703  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1708  ldstr    aAdding0DaysToT// "Adding {0} days to the date threw excep"...
0x170d  ldc.i4.1
0x170e  newarr   [mscorlib]System.Object
0x1713  dup
0x1714  ldc.i4.0
0x1715  ldarg.2
0x1716  box      [mscorlib]System.Int32
0x171b  stelem.ref
0x171c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1721  ldloc.1
0x1722  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InvalidTransformationExecutionException::.ctor(string, class [mscorlib]System.Exception)
0x1727  throw
0x1728  ldarg.s  5
0x172a  ldc.i4.1
0x172b  bne.un.s loc_1760
0x172d  ldloca.s 0
0x172f  ldarg.s  4
0x1731  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMonths(int32)
0x1736  stloc.0
0x1737  leave.s  loc_1760
0x1739  stloc.2
0x173a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x173f  ldstr    aAdding0MonthsT// "Adding {0} months to the date threw exc"...
0x1744  ldc.i4.1
0x1745  newarr   [mscorlib]System.Object
0x174a  dup
0x174b  ldc.i4.0
0x174c  ldarg.s  4
0x174e  box      [mscorlib]System.Int32
0x1753  stelem.ref
0x1754  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1759  ldloc.2
0x175a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InvalidTransformationExecutionException::.ctor(string, class [mscorlib]System.Exception)
0x175f  throw
0x1760  ldarg.s  7
0x1762  ldc.i4.1
0x1763  bne.un.s loc_1798
0x1765  ldloca.s 0
0x1767  ldarg.s  6
0x1769  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddYears(int32)
0x176e  stloc.0
0x176f  leave.s  loc_1798
0x1771  stloc.3
0x1772  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1777  ldstr    aAdding0YearsTo// "Adding {0} years to the date threw exce"...
0x177c  ldc.i4.1
0x177d  newarr   [mscorlib]System.Object
0x1782  dup
0x1783  ldc.i4.0
0x1784  ldarg.s  6
0x1786  box      [mscorlib]System.Int32
0x178b  stelem.ref
0x178c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1791  ldloc.3
0x1792  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InvalidTransformationExecutionException::.ctor(string, class [mscorlib]System.Exception)
0x1797  throw
0x1798  ldloc.0
0x1799  ret
```
