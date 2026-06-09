# Microsoft.Crm.Asynchronous.SynchronousQueueManager`1::ExecuteQueueManagementOperationForAllOrganizationWithMetric

- ea: `0x10550`
- end: `0x10591`
- name: `Microsoft.Crm.Asynchronous.SynchronousQueueManager`1::ExecuteQueueManagementOperationForAllOrganizationWithMetric`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14d20`
- `0x15810`

## string_xrefs

- `0x1055e`: `Composite operation should implement IServiceOperation`

## pseudocode

```c

```

## disassembly

```asm
0x10550  ldarg.0
0x10551  ldarg.1
0x10552  ldarg.2
0x10553  ldarg.s  4
0x10555  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation class Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<var<u1>>::CreateQueueManagementOperationForAllOrganization(string, class OrganizationQueueDataAccessHandler<var<u1>>, !!T0)
0x1055a  dup
0x1055b  ldnull
0x1055c  cgt.un
0x1055e  ldstr    aCompositeOpera_0// "Composite operation should implement IS"...
0x10563  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x10568  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1056d  stloc.0
0x1056e  dup
0x1056f  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x10574  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x10579  stloc.1
0x1057a  ldloca.s 1
0x1057c  ldloc.0
0x1057d  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x10582  stloc.2
0x10583  ldloca.s 2
0x10585  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x1058a  conv.i8
0x1058b  call     void Microsoft.Crm.Asynchronous.AsyncTimeUntilLockMetric::ReportValue(int64 time)
0x10590  ret
```
