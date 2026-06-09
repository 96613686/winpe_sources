# Microsoft.Crm.Sdk.InProcessCrmService::Dispose

- ea: `0x34a0`
- end: `0x34ae`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::Dispose`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8210`

## callees

- `0x34b0`

## pseudocode

```c

```

## disassembly

```asm
0x34a0  ldarg.0
0x34a1  ldc.i4.1
0x34a2  call     instance void Microsoft.Crm.Sdk.InProcessCrmService::Dispose(bool disposing)
0x34a7  ldarg.0
0x34a8  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x34ad  ret
```
