# AsyncOperationPerformanceCounters::.ctor

- ea: `0x15ce0`
- end: `0x15efb`
- name: `AsyncOperationPerformanceCounters::.ctor`
- size: `539`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2070`
- `0x164e0`

## callees

- `0x800`

## string_xrefs

- `0x15ced`: `{0} Operations Completed`
- `0x15d13`: `{0} Operations Completion Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x15ce0  ldarg.0
0x15ce1  call     instance void [mscorlib]System.Object::.ctor()
0x15ce6  ldarg.0
0x15ce7  ldarg.1
0x15ce8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15ced  ldstr    a0OperationsCom// "{0} Operations Completed"
0x15cf2  ldc.i4.1
0x15cf3  newarr   [mscorlib]System.Object
0x15cf8  dup
0x15cf9  ldc.i4.0
0x15cfa  ldarg.2
0x15cfb  stelem.ref
0x15cfc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15d01  ldarg.3
0x15d02  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15d07  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsCompleted
0x15d0c  ldarg.0
0x15d0d  ldarg.1
0x15d0e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15d13  ldstr    a0OperationsCom_0// "{0} Operations Completion Throughput"
0x15d18  ldc.i4.1
0x15d19  newarr   [mscorlib]System.Object
0x15d1e  dup
0x15d1f  ldc.i4.0
0x15d20  ldarg.2
0x15d21  stelem.ref
0x15d22  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15d27  ldarg.3
0x15d28  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15d2d  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsCompletedThroughput
0x15d32  ldarg.0
0x15d33  ldarg.1
0x15d34  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15d39  ldstr    a0OperationsExe// "{0} Operations Executing"
0x15d3e  ldc.i4.1
0x15d3f  newarr   [mscorlib]System.Object
0x15d44  dup
0x15d45  ldc.i4.0
0x15d46  ldarg.2
0x15d47  stelem.ref
0x15d48  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15d4d  ldarg.3
0x15d4e  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15d53  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsExecuting
0x15d58  ldarg.0
0x15d59  ldarg.1
0x15d5a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15d5f  ldstr    a0OperationsFai// "{0} Operations Failed"
0x15d64  ldc.i4.1
0x15d65  newarr   [mscorlib]System.Object
0x15d6a  dup
0x15d6b  ldc.i4.0
0x15d6c  ldarg.2
0x15d6d  stelem.ref
0x15d6e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15d73  ldarg.3
0x15d74  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15d79  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsFailedWithException
0x15d7e  ldarg.0
0x15d7f  ldarg.1
0x15d80  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15d85  ldstr    a0OperationsFai_0// "{0} Operations Failed With Retry"
0x15d8a  ldc.i4.1
0x15d8b  newarr   [mscorlib]System.Object
0x15d90  dup
0x15d91  ldc.i4.0
0x15d92  ldarg.2
0x15d93  stelem.ref
0x15d94  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15d99  ldarg.3
0x15d9a  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15d9f  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsFailedWithRetry
0x15da4  ldarg.0
0x15da5  ldarg.1
0x15da6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15dab  ldstr    a0OperationsOut// "{0} Operations Outstanding"
0x15db0  ldc.i4.1
0x15db1  newarr   [mscorlib]System.Object
0x15db6  dup
0x15db7  ldc.i4.0
0x15db8  ldarg.2
0x15db9  stelem.ref
0x15dba  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15dbf  ldarg.3
0x15dc0  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15dc5  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsOutstanding
0x15dca  ldarg.0
0x15dcb  ldarg.1
0x15dcc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15dd1  ldstr    aRateOf0Operati// "Rate of {0} Operations Failed With Exce"...
0x15dd6  ldc.i4.1
0x15dd7  newarr   [mscorlib]System.Object
0x15ddc  dup
0x15ddd  ldc.i4.0
0x15dde  ldarg.2
0x15ddf  stelem.ref
0x15de0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15de5  ldarg.3
0x15de6  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15deb  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_rateFailedWithException
0x15df0  ldarg.0
0x15df1  ldarg.1
0x15df2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15df7  ldstr    aRateOf0Operati_0// "Rate of {0} Operations Failed With Retr"...
0x15dfc  ldc.i4.1
0x15dfd  newarr   [mscorlib]System.Object
0x15e02  dup
0x15e03  ldc.i4.0
0x15e04  ldarg.2
0x15e05  stelem.ref
0x15e06  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15e0b  ldarg.3
0x15e0c  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15e11  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_rateFailedWithRetry
0x15e16  ldarg.0
0x15e17  ldarg.1
0x15e18  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15e1d  ldstr    a0AverageTimeSp// "{0} - Average time spent in operation"
0x15e22  ldc.i4.1
0x15e23  newarr   [mscorlib]System.Object
0x15e28  dup
0x15e29  ldc.i4.0
0x15e2a  ldarg.2
0x15e2b  stelem.ref
0x15e2c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15e31  ldarg.3
0x15e32  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15e37  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_averageExecutionTime
0x15e3c  ldarg.0
0x15e3d  ldarg.1
0x15e3e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15e43  ldstr    a0AverageTimeSp_0// "{0} - Average time spent in waiting sta"...
0x15e48  ldc.i4.1
0x15e49  newarr   [mscorlib]System.Object
0x15e4e  dup
0x15e4f  ldc.i4.0
0x15e50  ldarg.2
0x15e51  stelem.ref
0x15e52  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15e57  ldarg.3
0x15e58  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15e5d  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_averageWaitingTime
0x15e62  ldarg.0
0x15e63  ldarg.1
0x15e64  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15e69  ldstr    a0AverageTimeSp_1// "{0} - Average time spent in throttled s"...
0x15e6e  ldc.i4.1
0x15e6f  newarr   [mscorlib]System.Object
0x15e74  dup
0x15e75  ldc.i4.0
0x15e76  ldarg.2
0x15e77  stelem.ref
0x15e78  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15e7d  ldarg.3
0x15e7e  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15e83  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_averageThrottledTime
0x15e88  ldarg.0
0x15e89  ldarg.1
0x15e8a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15e8f  ldstr    a0OperationsWai// "{0} Operations Waiting on I/O"
0x15e94  ldc.i4.1
0x15e95  newarr   [mscorlib]System.Object
0x15e9a  dup
0x15e9b  ldc.i4.0
0x15e9c  ldarg.2
0x15e9d  stelem.ref
0x15e9e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15ea3  ldarg.3
0x15ea4  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15ea9  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsWaiting
0x15eae  ldarg.0
0x15eaf  ldarg.1
0x15eb0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15eb5  ldstr    a0OperationsThr// "{0} Operations Throttled"
0x15eba  ldc.i4.1
0x15ebb  newarr   [mscorlib]System.Object
0x15ec0  dup
0x15ec1  ldc.i4.0
0x15ec2  ldarg.2
0x15ec3  stelem.ref
0x15ec4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15ec9  ldarg.3
0x15eca  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15ecf  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsThrottled
0x15ed4  ldarg.0
0x15ed5  ldarg.1
0x15ed6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15edb  ldstr    a0OperationsRes// "{0} Operations Resumed Prematurely"
0x15ee0  ldc.i4.1
0x15ee1  newarr   [mscorlib]System.Object
0x15ee6  dup
0x15ee7  ldc.i4.0
0x15ee8  ldarg.2
0x15ee9  stelem.ref
0x15eea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15eef  ldarg.3
0x15ef0  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x15ef5  stfld    class [System]System.Diagnostics.PerformanceCounter AsyncOperationPerformanceCounters::_itemsPrematurelyResumed
0x15efa  ret
```
