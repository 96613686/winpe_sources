# Microsoft.Crm.Asynchronous.AsyncServiceBehaviorFactory::CreateBehaviors

- ea: `0x51d0`
- end: `0x51ea`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceBehaviorFactory::CreateBehaviors`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18c0`

## callees

- `0x30`
- `0xc40`
- `0x51d0`

## pseudocode

```c

```

## disassembly

```asm
0x51d0  ldarg.0
0x51d1  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x51d6  brfalse.s loc_51E3
0x51d8  ldarg.0
0x51d9  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x51de  ldc.i4.3
0x51df  beq.s    loc_51E3
0x51e1  ldnull
0x51e2  ret
0x51e3  ldarg.0
0x51e4  newobj   instance void Microsoft.Crm.OperationBehaviors.FaultToleranceBehavior::.ctor(class Microsoft.Crm.OperationBehaviors.IReliableService service)
0x51e9  ret
```
