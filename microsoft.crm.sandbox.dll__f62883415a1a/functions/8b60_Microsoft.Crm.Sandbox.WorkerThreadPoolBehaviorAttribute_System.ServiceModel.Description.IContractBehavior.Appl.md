# Microsoft.Crm.Sandbox.WorkerThreadPoolBehaviorAttribute::System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior

- ea: `0x8b60`
- end: `0x8b79`
- name: `Microsoft.Crm.Sandbox.WorkerThreadPoolBehaviorAttribute::System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x8b60`

## pseudocode

```c

```

## disassembly

```asm
0x8b60  ldc.i4.s 0x12
0x8b62  ldc.i4.1
0x8b63  call     T0x2B000008
0x8b68  ldc.i4.0
0x8b69  cgt
0x8b6b  brfalse.s loc_8B78
0x8b6d  ldarg.3
0x8b6e  ldsfld   class Microsoft.Crm.Sandbox.WorkerThreadPoolSynchronizer Microsoft.Crm.Sandbox.WorkerThreadPoolBehaviorAttribute::synchronizer
0x8b73  callvirt instance void [System.ServiceModel]System.ServiceModel.Dispatcher.DispatchRuntime::set_SynchronizationContext(class [mscorlib]System.Threading.SynchronizationContext)
0x8b78  ret
```
