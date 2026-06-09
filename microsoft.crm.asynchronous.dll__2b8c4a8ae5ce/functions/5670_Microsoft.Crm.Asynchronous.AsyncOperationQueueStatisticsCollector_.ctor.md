# Microsoft.Crm.Asynchronous.AsyncOperationQueueStatisticsCollector::.ctor

- ea: `0x5670`
- end: `0x56b1`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueStatisticsCollector::.ctor`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf930`

## callees

- `0x124a0`

## string_xrefs

- `0x5685`: `Select SUM(Backlog) Backlog, Max(Latency) as Latency FROM\n					(\n						SELECT COUNT(*) AS Backlog,\n							CONVERT(INT, MAX(DATEDIFF(ss, postponeuntil , GETUTCDATE()))) AS Latency \n							FROM AsyncOperationBase WITH(NOLOCK)\n							WHERE \n							(StateCode = 1 AND DependencyToken is NULL AND postponeuntil < DateAdd(mi, @InternalSLA, GETUTCDATE()) AND\n							DATEDIFF(YEAR, postponeuntil, GETUTCDATE()) >= 0 and DATEDIFF(YEAR, postponeuntil, GETUTCDATE()) <= 1)\n						UNION ALL					\`

## pseudocode

```c

```

## disassembly

```asm
0x5670  ldarg.0
0x5671  ldstr    aDeclareInterna_0// "declare @InternalSLA int = "
0x5676  ldsfld   int32 Microsoft.Crm.Asynchronous.AsyncOperationQueueStatisticsCollector::InternalSla
0x567b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5680  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x5685  ldstr    aSelectSumBackl// "Select SUM(Backlog) Backlog, Max(Latenc"...
0x568a  call     string [mscorlib]System.String::Concat(string, string, string)
0x568f  stfld    string Microsoft.Crm.Asynchronous.AsyncOperationQueueStatisticsCollector::AsyncOperationQueueBacklogQuery
0x5694  ldarg.0
0x5695  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x569a  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncOperationQueueStatisticsCollector::_lastExecutionTime
0x569f  ldarg.0
0x56a0  call     instance void [mscorlib]System.Object::.ctor()
0x56a5  ldarg.0
0x56a6  newobj   instance void Microsoft.Crm.Asynchronous.QueueStatisticsHelper::.ctor()
0x56ab  stfld    class Microsoft.Crm.Asynchronous.QueueStatisticsHelper Microsoft.Crm.Asynchronous.AsyncOperationQueueStatisticsCollector::_queueStatisticsHelper
0x56b0  ret
```
