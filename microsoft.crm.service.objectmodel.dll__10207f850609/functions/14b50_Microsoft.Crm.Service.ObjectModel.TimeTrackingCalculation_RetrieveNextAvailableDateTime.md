# Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::RetrieveNextAvailableDateTime

- ea: `0x14b50`
- end: `0x14c62`
- name: `Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::RetrieveNextAvailableDateTime`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14990`

## callees

- `0x14b50`
- `0x1afb0`
- `0x1afd0`

## pseudocode

```c

```

## disassembly

```asm
0x14b50  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x14b55  stloc.0
0x14b56  ldloc.0
0x14b57  ldarg.2
0x14b58  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::startDate
0x14b5d  newobj   instance void <>c__DisplayClass15_1::.ctor()
0x14b62  stloc.2
0x14b63  ldloc.2
0x14b64  ldloc.0
0x14b65  stfld    class <>c__DisplayClass15_0 <>c__DisplayClass15_1::CS$<>8__locals1
0x14b6a  ldloc.2
0x14b6b  ldc.i4.1
0x14b6c  stfld    int32 <>c__DisplayClass15_1::numberOfDays
0x14b71  br       loc_14C4F
0x14b76  ldarg.0
0x14b77  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x14b7c  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.DayOfWeek, float64> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_AvailableMinutesInaDay()
0x14b81  ldloc.2
0x14b82  ldfld    class <>c__DisplayClass15_0 <>c__DisplayClass15_1::CS$<>8__locals1
0x14b87  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::startDate
0x14b8c  ldloc.2
0x14b8d  ldfld    int32 <>c__DisplayClass15_1::numberOfDays
0x14b92  conv.r8
0x14b93  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x14b98  stloc.3
0x14b99  ldloca.s 3
0x14b9b  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x14ba0  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.DayOfWeek, float64>::get_Item(void)
0x14ba5  conv.r8
0x14ba6  ldc.r8   0.0
0x14baf  ble.un   loc_14C3D
0x14bb4  ldarg.1
0x14bb5  ldloc.2
0x14bb6  ldftn    instance bool <>c__DisplayClass15_1::<RetrieveNextAvailableDateTime>b__0(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo value)
0x14bbc  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool>::.ctor(object, native int)
0x14bc1  call     T0x2B000009
0x14bc6  call     T0x2B00000A
0x14bcb  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool> <>c::<>9__15_1
0x14bd0  dup
0x14bd1  brtrue.s loc_14BEA
0x14bd3  pop
0x14bd4  ldsfld   class <>c <>c::<>9
0x14bd9  ldftn    instance bool <>c::<RetrieveNextAvailableDateTime>b__15_1(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo x)
0x14bdf  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool>::.ctor(object, native int)
0x14be4  dup
0x14be5  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool> <>c::<>9__15_1
0x14bea  call     T0x2B000009
0x14bef  call     T0x2B00000B
0x14bf4  stloc.1
0x14bf5  ldloc.2
0x14bf6  ldfld    class <>c__DisplayClass15_0 <>c__DisplayClass15_1::CS$<>8__locals1
0x14bfb  ldloc.2
0x14bfc  ldfld    class <>c__DisplayClass15_0 <>c__DisplayClass15_1::CS$<>8__locals1
0x14c01  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::startDate
0x14c06  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x14c0b  stloc.3
0x14c0c  ldloca.s 3
0x14c0e  ldloc.2
0x14c0f  ldfld    int32 <>c__DisplayClass15_1::numberOfDays
0x14c14  conv.r8
0x14c15  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x14c1a  stloc.3
0x14c1b  ldloca.s 3
0x14c1d  ldloc.1
0x14c1e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14c23  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14c28  stloc.s  4
0x14c2a  ldloca.s 4
0x14c2c  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14c31  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x14c36  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::startDate
0x14c3b  br.s     loc_14C5B
0x14c3d  ldloc.2
0x14c3e  ldfld    int32 <>c__DisplayClass15_1::numberOfDays
0x14c43  stloc.s  5
0x14c45  ldloc.2
0x14c46  ldloc.s  5
0x14c48  ldc.i4.1
0x14c49  add
0x14c4a  stfld    int32 <>c__DisplayClass15_1::numberOfDays
0x14c4f  ldloc.2
0x14c50  ldfld    int32 <>c__DisplayClass15_1::numberOfDays
0x14c55  ldc.i4.7
0x14c56  ble      loc_14B76
0x14c5b  ldloc.0
0x14c5c  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::startDate
0x14c61  ret
```
