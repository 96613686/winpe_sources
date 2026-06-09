# Microsoft.Crm.Asynchronous.AsyncService::OnContinue

- ea: `0x1240`
- end: `0x1266`
- name: `Microsoft.Crm.Asynchronous.AsyncService::OnContinue`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1650`

## string_xrefs

- `0x1254`: `Resuming service`

## pseudocode

```c

```

## disassembly

```asm
0x1240  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1245  ldc.i4.s 0x15
0x1247  ldstr    a0// "{0}"
0x124c  ldc.i4.1
0x124d  newarr   [mscorlib]System.Object
0x1252  dup
0x1253  ldc.i4.0
0x1254  ldstr    aResumingServic// "Resuming service"
0x1259  stelem.ref
0x125a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x125f  ldarg.0
0x1260  call     instance void Microsoft.Crm.Asynchronous.AsyncService::StartComponents()
0x1265  ret
```
