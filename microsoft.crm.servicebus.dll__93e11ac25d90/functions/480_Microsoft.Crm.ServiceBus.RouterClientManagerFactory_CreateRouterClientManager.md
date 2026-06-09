# Microsoft.Crm.ServiceBus.RouterClientManagerFactory::CreateRouterClientManager

- ea: `0x480`
- end: `0x4aa`
- name: `Microsoft.Crm.ServiceBus.RouterClientManagerFactory::CreateRouterClientManager`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x4c0`

## callees

- `0x480`
- `0x640`
- `0x680`

## pseudocode

```c

```

## disassembly

```asm
0x480  ldc.i4.0
0x481  ldstr    aPostviaexterna// "PostViaExternalRouter"
0x486  ldc.i4.0
0x487  box      [mscorlib]System.Int32
0x48c  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x491  unbox.any [mscorlib]System.Int32
0x496  clt
0x498  brtrue.s loc_4A2
0x49a  newobj   instance void Microsoft.Crm.ServiceBus.RouterClientManagerInProc::.ctor()
0x49f  stloc.0
0x4a0  ldloc.0
0x4a1  ret
0x4a2  newobj   instance void Microsoft.Crm.ServiceBus.RouterClientManagerExternal::.ctor()
0x4a7  stloc.0
0x4a8  ldloc.0
0x4a9  ret
```
