# Microsoft.Crm.ServiceBus.WebhookClient::GetCrmExceptionWithInnerException

- ea: `0x6330`
- end: `0x6345`
- name: `Microsoft.Crm.ServiceBus.WebhookClient::GetCrmExceptionWithInnerException`
- size: `21`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x60b0`
- `0x6100`
- `0x63e0`
- `0x68c0`
- `0x6c10`

## pseudocode

```c

```

## disassembly

```asm
0x6330  ldarg.1
0x6331  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x6336  ldarg.2
0x6337  ldc.i4.s 0x40
0x6339  ldc.i4.0
0x633a  newarr   [mscorlib]System.Object
0x633f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, object[])
0x6344  ret
```
