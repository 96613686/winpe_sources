# Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::CreateInstance

- ea: `0x6dd0`
- end: `0x6e5c`
- name: `Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::CreateInstance`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x6e70`
- `0x6e90`
- `0x6ea0`
- `0x6eb0`
- `0x6ed0`
- `0x6ef0`
- `0x6f00`

## pseudocode

```c

```

## disassembly

```asm
0x6dd0  ldarg.0
0x6dd1  ldstr    aBag// "bag"
0x6dd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6ddb  newobj   instance void Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::.ctor()
0x6de0  stloc.0
0x6de1  ldloc.0
0x6de2  ldarg.0
0x6de3  ldstr    aId// "Id"
0x6de8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6ded  unbox.any [mscorlib]System.Guid
0x6df2  callvirt instance void Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::set_Id(valuetype [mscorlib]System.Guid value)
0x6df7  ldloc.0
0x6df8  ldarg.0
0x6df9  ldstr    aOperationtype// "OperationType"
0x6dfe  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6e03  unbox.any Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobOperationType
0x6e08  callvirt instance void Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::set_OperationType(valuetype Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobOperationType value)
0x6e0d  ldloc.0
0x6e0e  ldarg.0
0x6e0f  ldstr    aLastruntime// "LastRunTime"
0x6e14  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6e19  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x6e1e  callvirt instance void Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::set_LastRuntime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x6e23  ldloc.0
0x6e24  ldarg.0
0x6e25  ldstr    aFrequencyinsec// "FrequencyInSeconds"
0x6e2a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6e2f  unbox.any [mscorlib]System.Int32
0x6e34  callvirt instance void Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::set_FrequencyInSeconds(int32 value)
0x6e39  ldloc.0
0x6e3a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6e3f  ldloc.0
0x6e40  callvirt instance int32 Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::get_FrequencyInSeconds()
0x6e45  conv.r8
0x6e46  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x6e4b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x6e50  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x6e55  callvirt instance void Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobData::set_NextRuntime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x6e5a  ldloc.0
0x6e5b  ret
```
