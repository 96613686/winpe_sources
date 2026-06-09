# Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::RetrieveAllReadyJobs

- ea: `0x6770`
- end: `0x6921`
- name: `Microsoft.Crm.Asynchronous.ScalegroupMaintenanceJobsMonitor::RetrieveAllReadyJobs`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6430`

## callees

- `0x6770`

## string_xrefs

- `0x68ed`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\ScalegroupMaintenanceJobsMonitor.cs`
- `0x68e8`: `RetrieveAllReadyJobs`

## pseudocode

```c

```

## disassembly

```asm
0x6770  ldc.i4.4
0x6771  newarr   [mscorlib]System.String
0x6776  dup
0x6777  ldc.i4.0
0x6778  ldstr    aId// "Id"
0x677d  stelem.ref
0x677e  dup
0x677f  ldc.i4.1
0x6780  ldstr    aOperationtype// "OperationType"
0x6785  stelem.ref
0x6786  dup
0x6787  ldc.i4.2
0x6788  ldstr    aFrequencyinsec// "FrequencyInSeconds"
0x678d  stelem.ref
0x678e  dup
0x678f  ldc.i4.3
0x6790  ldstr    aLastruntime// "LastRunTime"
0x6795  stelem.ref
0x6796  stloc.0
0x6797  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x679c  stloc.1
0x679d  ldc.i4.3
0x679e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x67a3  box      [mscorlib]System.DateTime
0x67a8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x67ad  stloc.2
0x67ae  ldloc.1
0x67af  ldstr    aNextruntime_0// "NextRunTime"
0x67b4  ldloc.2
0x67b5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x67ba  ldloc.1
0x67bb  ldstr    aIsrunning// "IsRunning"
0x67c0  ldc.i4.0
0x67c1  box      [mscorlib]System.Boolean
0x67c6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x67cb  ldloc.1
0x67cc  ldstr    aEnabled// "Enabled"
0x67d1  ldc.i4.1
0x67d2  box      [mscorlib]System.Boolean
0x67d7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x67dc  ldloc.1
0x67dd  ldstr    aHost// "Host"
0x67e2  call     string [mscorlib]System.Environment::get_MachineName()
0x67e7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x67ec  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x67f1  stloc.3
0x67f2  ldloc.3
0x67f3  ldstr    aNextruntime_0// "NextRunTime"
0x67f8  ldnull
0x67f9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x67fe  ldloc.3
0x67ff  ldstr    aIsrunning// "IsRunning"
0x6804  ldc.i4.0
0x6805  box      [mscorlib]System.Boolean
0x680a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x680f  ldloc.3
0x6810  ldstr    aEnabled// "Enabled"
0x6815  ldc.i4.1
0x6816  box      [mscorlib]System.Boolean
0x681b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6820  ldloc.3
0x6821  ldstr    aHost// "Host"
0x6826  call     string [mscorlib]System.Environment::get_MachineName()
0x682b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6830  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x6835  stloc.s  4
0x6837  ldloc.s  4
0x6839  ldstr    aNextruntime_0// "NextRunTime"
0x683e  ldloc.2
0x683f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6844  ldloc.s  4
0x6846  ldstr    aIsrunning// "IsRunning"
0x684b  ldc.i4.0
0x684c  box      [mscorlib]System.Boolean
0x6851  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6856  ldloc.s  4
0x6858  ldstr    aEnabled// "Enabled"
0x685d  ldc.i4.1
0x685e  box      [mscorlib]System.Boolean
0x6863  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x6868  ldloc.s  4
0x686a  ldstr    aHostlocked// "HostLocked"
0x686f  ldc.i4.0
0x6870  box      [mscorlib]System.Boolean
0x6875  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x687a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x687f  stloc.s  5
0x6881  ldloc.s  5
0x6883  ldstr    aNextruntime_0// "NextRunTime"
0x6888  ldnull
0x6889  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x688e  ldloc.s  5
0x6890  ldstr    aIsrunning// "IsRunning"
0x6895  ldc.i4.0
0x6896  box      [mscorlib]System.Boolean
0x689b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x68a0  ldloc.s  5
0x68a2  ldstr    aEnabled// "Enabled"
0x68a7  ldc.i4.1
0x68a8  box      [mscorlib]System.Boolean
0x68ad  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x68b2  ldloc.s  5
0x68b4  ldstr    aHostlocked// "HostLocked"
0x68b9  ldc.i4.0
0x68ba  box      [mscorlib]System.Boolean
0x68bf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x68c4  ldarg.1
0x68c5  ldstr    aScalegroupmain_0// "ScaleGroupMaintenanceJobs"
0x68ca  ldloc.0
0x68cb  ldc.i4.4
0x68cc  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x68d1  dup
0x68d2  ldc.i4.0
0x68d3  ldloc.1
0x68d4  stelem.ref
0x68d5  dup
0x68d6  ldc.i4.1
0x68d7  ldloc.3
0x68d8  stelem.ref
0x68d9  dup
0x68da  ldc.i4.2
0x68db  ldloc.s  4
0x68dd  stelem.ref
0x68de  dup
0x68df  ldc.i4.3
0x68e0  ldloc.s  5
0x68e2  stelem.ref
0x68e3  ldc.i4   0x106
0x68e8  ldstr    aRetrieveallrea// "RetrieveAllReadyJobs"
0x68ed  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x68f2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x68f7  stloc.s  6
0x68f9  ldloc.s  6
0x68fb  brtrue.s loc_6903
0x68fd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData>::.ctor()
0x6902  ret
0x6903  ldloc.s  6
0x6905  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x690a  ldnull
0x690b  ldftn    class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::CreateInstance(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x6911  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData>::.ctor(object, native int)
0x6916  call     T0x2B000014
0x691b  call     T0x2B000015
0x6920  ret
```
