# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::LogCrmTraceAndEventLog

- ea: `0x8950`
- end: `0x89a6`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::LogCrmTraceAndEventLog`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x61f0`

## callees

- `0x8ab0`
- `0x8ad0`

## pseudocode

```c

```

## disassembly

```asm
0x8950  ldnull
0x8951  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x8956  ldc.i4.6
0x8957  ldstr    a01_2// "{0} - {1}"
0x895c  ldc.i4.2
0x895d  newarr   [mscorlib]System.Object
0x8962  dup
0x8963  ldc.i4.0
0x8964  ldarg.2
0x8965  stelem.ref
0x8966  dup
0x8967  ldc.i4.1
0x8968  ldarg.3
0x8969  stelem.ref
0x896a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x896f  ldarg.0
0x8970  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog Microsoft.Crm.Asynchronous.ResourceBookingSyncService::eventLog
0x8975  ldc.i4.1
0x8976  ldarg.1
0x8977  ldc.i4.3
0x8978  newarr   [mscorlib]System.Object
0x897d  dup
0x897e  ldc.i4.0
0x897f  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x8984  stloc.0
0x8985  ldloca.s 0
0x8987  constrained. [mscorlib]System.Guid
0x898d  callvirt instance string [mscorlib]System.Object::ToString()
0x8992  stelem.ref
0x8993  dup
0x8994  ldc.i4.1
0x8995  ldarg.0
0x8996  call     instance string Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationName()
0x899b  stelem.ref
0x899c  dup
0x899d  ldc.i4.2
0x899e  ldarg.3
0x899f  stelem.ref
0x89a0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x89a5  ret
```
