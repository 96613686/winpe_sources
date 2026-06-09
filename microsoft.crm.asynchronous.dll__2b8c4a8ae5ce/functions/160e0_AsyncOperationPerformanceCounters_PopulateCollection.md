# AsyncOperationPerformanceCounters::PopulateCollection

- ea: `0x160e0`
- end: `0x1648b`
- name: `AsyncOperationPerformanceCounters::PopulateCollection`
- size: `939`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1e90`
- `0x164b0`

## string_xrefs

- `0x160e6`: `{0} Operations Completed`
- `0x16129`: `{0} Operations Completion Throughput`
- `0x160ff`: `The total number of {0} operations completed.`
- `0x16142`: `Completion throughput of {0} operations.`

## pseudocode

```c

```

## disassembly

```asm
0x160e0  ldarg.0
0x160e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x160e6  ldstr    a0OperationsCom// "{0} Operations Completed"
0x160eb  ldc.i4.1
0x160ec  newarr   [mscorlib]System.Object
0x160f1  dup
0x160f2  ldc.i4.0
0x160f3  ldarg.1
0x160f4  stelem.ref
0x160f5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x160fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x160ff  ldstr    aTheTotalNumber// "The total number of {0} operations comp"...
0x16104  ldc.i4.1
0x16105  newarr   [mscorlib]System.Object
0x1610a  dup
0x1610b  ldc.i4.0
0x1610c  ldarg.1
0x1610d  stelem.ref
0x1610e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16113  ldc.i4   0x10100
0x16118  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1611d  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x16122  pop
0x16123  ldarg.0
0x16124  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16129  ldstr    a0OperationsCom_0// "{0} Operations Completion Throughput"
0x1612e  ldc.i4.1
0x1612f  newarr   [mscorlib]System.Object
0x16134  dup
0x16135  ldc.i4.0
0x16136  ldarg.1
0x16137  stelem.ref
0x16138  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1613d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16142  ldstr    aCompletionThro// "Completion throughput of {0} operations"...
0x16147  ldc.i4.1
0x16148  newarr   [mscorlib]System.Object
0x1614d  dup
0x1614e  ldc.i4.0
0x1614f  ldarg.1
0x16150  stelem.ref
0x16151  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16156  ldc.i4   0x10410500
0x1615b  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x16160  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x16165  pop
0x16166  ldarg.0
0x16167  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1616c  ldstr    a0OperationsExe// "{0} Operations Executing"
0x16171  ldc.i4.1
0x16172  newarr   [mscorlib]System.Object
0x16177  dup
0x16178  ldc.i4.0
0x16179  ldarg.1
0x1617a  stelem.ref
0x1617b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16180  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16185  ldstr    aTheCurrentNumb// "The current number of {0} operations be"...
0x1618a  ldc.i4.1
0x1618b  newarr   [mscorlib]System.Object
0x16190  dup
0x16191  ldc.i4.0
0x16192  ldarg.1
0x16193  stelem.ref
0x16194  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16199  ldc.i4   0x10100
0x1619e  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x161a3  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x161a8  pop
0x161a9  ldarg.0
0x161aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x161af  ldstr    a0OperationsFai// "{0} Operations Failed"
0x161b4  ldc.i4.1
0x161b5  newarr   [mscorlib]System.Object
0x161ba  dup
0x161bb  ldc.i4.0
0x161bc  ldarg.1
0x161bd  stelem.ref
0x161be  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x161c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x161c8  ldstr    aTheTotalNumber_0// "The total number of {0} operations fail"...
0x161cd  ldc.i4.1
0x161ce  newarr   [mscorlib]System.Object
0x161d3  dup
0x161d4  ldc.i4.0
0x161d5  ldarg.1
0x161d6  stelem.ref
0x161d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x161dc  ldc.i4   0x10100
0x161e1  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x161e6  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x161eb  pop
0x161ec  ldarg.0
0x161ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x161f2  ldstr    a0OperationsFai_0// "{0} Operations Failed With Retry"
0x161f7  ldc.i4.1
0x161f8  newarr   [mscorlib]System.Object
0x161fd  dup
0x161fe  ldc.i4.0
0x161ff  ldarg.1
0x16200  stelem.ref
0x16201  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16206  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1620b  ldstr    aTheTotalNumber_1// "The total number of {0} operations fail"...
0x16210  ldc.i4.1
0x16211  newarr   [mscorlib]System.Object
0x16216  dup
0x16217  ldc.i4.0
0x16218  ldarg.1
0x16219  stelem.ref
0x1621a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1621f  ldc.i4   0x10100
0x16224  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x16229  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1622e  pop
0x1622f  ldarg.0
0x16230  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16235  ldstr    a0OperationsOut// "{0} Operations Outstanding"
0x1623a  ldc.i4.1
0x1623b  newarr   [mscorlib]System.Object
0x16240  dup
0x16241  ldc.i4.0
0x16242  ldarg.1
0x16243  stelem.ref
0x16244  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16249  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1624e  ldstr    aTheCurrentNumb_0// "The current number of {0} operations ou"...
0x16253  ldc.i4.1
0x16254  newarr   [mscorlib]System.Object
0x16259  dup
0x1625a  ldc.i4.0
0x1625b  ldarg.1
0x1625c  stelem.ref
0x1625d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16262  ldc.i4   0x10100
0x16267  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1626c  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x16271  pop
0x16272  ldarg.0
0x16273  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16278  ldstr    aRateOf0Operati// "Rate of {0} Operations Failed With Exce"...
0x1627d  ldc.i4.1
0x1627e  newarr   [mscorlib]System.Object
0x16283  dup
0x16284  ldc.i4.0
0x16285  ldarg.1
0x16286  stelem.ref
0x16287  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1628c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16291  ldstr    aRateOf0Operati_1// "Rate of {0} operations failed with exce"...
0x16296  ldc.i4.1
0x16297  newarr   [mscorlib]System.Object
0x1629c  dup
0x1629d  ldc.i4.0
0x1629e  ldarg.1
0x1629f  stelem.ref
0x162a0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x162a5  ldc.i4   0x10100
0x162aa  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x162af  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x162b4  pop
0x162b5  ldarg.0
0x162b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x162bb  ldstr    aRateOf0Operati_0// "Rate of {0} Operations Failed With Retr"...
0x162c0  ldc.i4.1
0x162c1  newarr   [mscorlib]System.Object
0x162c6  dup
0x162c7  ldc.i4.0
0x162c8  ldarg.1
0x162c9  stelem.ref
0x162ca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x162cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x162d4  ldstr    aRateOf0Operati_2// "Rate of {0} operations failed with retr"...
0x162d9  ldc.i4.1
0x162da  newarr   [mscorlib]System.Object
0x162df  dup
0x162e0  ldc.i4.0
0x162e1  ldarg.1
0x162e2  stelem.ref
0x162e3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x162e8  ldc.i4   0x10100
0x162ed  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x162f2  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x162f7  pop
0x162f8  ldarg.0
0x162f9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x162fe  ldstr    a0AverageTimeSp// "{0} - Average time spent in operation"
0x16303  ldc.i4.1
0x16304  newarr   [mscorlib]System.Object
0x16309  dup
0x1630a  ldc.i4.0
0x1630b  ldarg.1
0x1630c  stelem.ref
0x1630d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16312  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16317  ldstr    a0AverageTimeSp_2// "{0} - Average time spent in operation."
0x1631c  ldc.i4.1
0x1631d  newarr   [mscorlib]System.Object
0x16322  dup
0x16323  ldc.i4.0
0x16324  ldarg.1
0x16325  stelem.ref
0x16326  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1632b  ldc.i4   0x10100
0x16330  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x16335  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1633a  pop
0x1633b  ldarg.0
0x1633c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16341  ldstr    a0AverageTimeSp_0// "{0} - Average time spent in waiting sta"...
0x16346  ldc.i4.1
0x16347  newarr   [mscorlib]System.Object
0x1634c  dup
0x1634d  ldc.i4.0
0x1634e  ldarg.1
0x1634f  stelem.ref
0x16350  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16355  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1635a  ldstr    a0AverageTimeSp_3// "{0} - Average time spent in waiting for"...
0x1635f  ldc.i4.1
0x16360  newarr   [mscorlib]System.Object
0x16365  dup
0x16366  ldc.i4.0
0x16367  ldarg.1
0x16368  stelem.ref
0x16369  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1636e  ldc.i4   0x10100
0x16373  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x16378  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1637d  pop
0x1637e  ldarg.0
0x1637f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16384  ldstr    a0AverageTimeSp_1// "{0} - Average time spent in throttled s"...
0x16389  ldc.i4.1
0x1638a  newarr   [mscorlib]System.Object
0x1638f  dup
0x16390  ldc.i4.0
0x16391  ldarg.1
0x16392  stelem.ref
0x16393  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16398  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1639d  ldstr    a0AverageTimeSp_4// "{0} - Average time spent in throttled s"...
0x163a2  ldc.i4.1
0x163a3  newarr   [mscorlib]System.Object
0x163a8  dup
0x163a9  ldc.i4.0
0x163aa  ldarg.1
0x163ab  stelem.ref
0x163ac  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x163b1  ldc.i4   0x10100
0x163b6  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x163bb  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x163c0  pop
0x163c1  ldarg.0
0x163c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x163c7  ldstr    a0OperationsWai// "{0} Operations Waiting on I/O"
0x163cc  ldc.i4.1
0x163cd  newarr   [mscorlib]System.Object
0x163d2  dup
0x163d3  ldc.i4.0
0x163d4  ldarg.1
0x163d5  stelem.ref
0x163d6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x163db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x163e0  ldstr    aTheCurrentNumb_1// "The current number of {0} operations wa"...
0x163e5  ldc.i4.1
0x163e6  newarr   [mscorlib]System.Object
0x163eb  dup
0x163ec  ldc.i4.0
0x163ed  ldarg.1
0x163ee  stelem.ref
0x163ef  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x163f4  ldc.i4   0x10100
0x163f9  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x163fe  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x16403  pop
0x16404  ldarg.0
0x16405  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1640a  ldstr    a0OperationsThr// "{0} Operations Throttled"
0x1640f  ldc.i4.1
0x16410  newarr   [mscorlib]System.Object
0x16415  dup
0x16416  ldc.i4.0
0x16417  ldarg.1
0x16418  stelem.ref
0x16419  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1641e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16423  ldstr    aTheCurrentNumb_2// "The current number of {0} throttled ope"...
0x16428  ldc.i4.1
0x16429  newarr   [mscorlib]System.Object
0x1642e  dup
0x1642f  ldc.i4.0
0x16430  ldarg.1
0x16431  stelem.ref
0x16432  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16437  ldc.i4   0x10100
0x1643c  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x16441  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x16446  pop
0x16447  ldarg.0
  ... truncated ...
```
