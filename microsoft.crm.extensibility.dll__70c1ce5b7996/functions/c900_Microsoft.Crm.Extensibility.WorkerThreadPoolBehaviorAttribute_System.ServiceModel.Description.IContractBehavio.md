# Microsoft.Crm.Extensibility.WorkerThreadPoolBehaviorAttribute::System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior

- ea: `0xc900`
- end: `0xc926`
- name: `Microsoft.Crm.Extensibility.WorkerThreadPoolBehaviorAttribute::System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xc900`

## string_xrefs

- `0xc900`: `UseWorkerThreads`

## pseudocode

```c

```

## disassembly

```asm
0xc900  ldstr    aUseworkerthrea// "UseWorkerThreads"
0xc905  ldc.i4.1
0xc906  box      [mscorlib]System.Int32
0xc90b  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xc910  unbox.any [mscorlib]System.Int32
0xc915  ldc.i4.0
0xc916  cgt
0xc918  brfalse.s loc_C925
0xc91a  ldarg.3
0xc91b  ldsfld   class Microsoft.Crm.Extensibility.WorkerThreadPoolSynchronizer Microsoft.Crm.Extensibility.WorkerThreadPoolBehaviorAttribute::synchronizer
0xc920  callvirt instance void [System.ServiceModel]System.ServiceModel.Dispatcher.DispatchRuntime::set_SynchronizationContext(class [mscorlib]System.Threading.SynchronizationContext)
0xc925  ret
```
