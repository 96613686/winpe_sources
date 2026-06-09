# Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::GetBusinessClosureDuration

- ea: `0x150b0`
- end: `0x15172`
- name: `Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::GetBusinessClosureDuration`
- size: `194`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14340`
- `0x150b0`
- `0x15180`

## callees

- `0x150b0`
- `0x1b0f0`

## pseudocode

```c

```

## disassembly

```asm
0x150b0  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x150b5  stloc.0
0x150b6  ldloc.0
0x150b7  ldarg.1
0x150b8  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass18_0::startDate
0x150bd  ldc.r8   0.0
0x150c6  stloc.1
0x150c7  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo> Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_holidayClosureList
0x150cc  brfalse.s loc_15135
0x150ce  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo> Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_holidayClosureList
0x150d3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo>::get_Count()
0x150d8  ldc.i4.0
0x150d9  ble.s    loc_15135
0x150db  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo> Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_holidayClosureList
0x150e0  ldloc.0
0x150e1  ldftn    instance bool <>c__DisplayClass18_0::<GetBusinessClosureDuration>b__0(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo value)
0x150e7  newobj   instance void class [mscorlib]System.Predicate`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo>::.ctor(object, native int)
0x150ec  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo>::Find(!!T0)
0x150f1  stloc.2
0x150f2  ldloc.2
0x150f3  brfalse.s loc_15114
0x150f5  ldloc.2
0x150f6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x150fb  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x15100  ldloc.0
0x15101  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass18_0::startDate
0x15106  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1510b  stloc.3
0x1510c  ldloca.s 3
0x1510e  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x15113  stloc.1
0x15114  ldloc.1
0x15115  ldc.r8   0.0
0x1511e  beq.s    loc_15135
0x15120  ldloc.1
0x15121  ldarg.0
0x15122  ldloc.0
0x15123  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass18_0::startDate
0x15128  ldloc.1
0x15129  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x1512e  call     instance float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::GetBusinessClosureDuration(valuetype [mscorlib]System.DateTime startDate)
0x15133  add
0x15134  stloc.1
0x15135  ldloc.1
0x15136  stloc.s  4
0x15138  leave.s  loc_1516F
0x1513a  stloc.s  5
0x1513c  ldloc.s  5
0x1513e  ldstr    aDetails0// "Details:{0}"
0x15143  ldc.i4.1
0x15144  newarr   [mscorlib]System.Object
0x15149  dup
0x1514a  ldc.i4.0
0x1514b  ldloc.s  5
0x1514d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x15152  stelem.ref
0x15153  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x15158  ldstr    aGetbusinessclo// "GetBusinessClosureDuration Failed "
0x1515d  ldloc.s  5
0x1515f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x15164  call     string [mscorlib]System.String::Concat(string, string)
0x15169  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1516e  throw
0x1516f  ldloc.s  4
0x15171  ret
```
