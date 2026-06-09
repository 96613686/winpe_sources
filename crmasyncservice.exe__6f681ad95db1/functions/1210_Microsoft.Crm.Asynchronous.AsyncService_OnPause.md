# Microsoft.Crm.Asynchronous.AsyncService::OnPause

- ea: `0x1210`
- end: `0x123c`
- name: `Microsoft.Crm.Asynchronous.AsyncService::OnPause`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1270`
- `0x16a0`

## string_xrefs

- `0x122a`: `Pausing service`

## pseudocode

```c

```

## disassembly

```asm
0x1210  ldarg.0
0x1211  call     instance void Microsoft.Crm.Asynchronous.AsyncService::WaitForStartupSequenceComplete()
0x1216  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x121b  ldc.i4.s 0x15
0x121d  ldstr    a0// "{0}"
0x1222  ldc.i4.1
0x1223  newarr   [mscorlib]System.Object
0x1228  dup
0x1229  ldc.i4.0
0x122a  ldstr    aPausingService// "Pausing service"
0x122f  stelem.ref
0x1230  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1235  ldarg.0
0x1236  call     instance void Microsoft.Crm.Asynchronous.AsyncService::StopComponents()
0x123b  ret
```
