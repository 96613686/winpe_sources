# Microsoft.Crm.ServiceBus.ServiceBusPlugin::.ctor

- ea: `0x790`
- end: `0x7b0`
- name: `Microsoft.Crm.ServiceBus.ServiceBusPlugin::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x790`

## string_xrefs

- `0x7a4`: `Input configuration should be a guid.`

## pseudocode

```c

```

## disassembly

```asm
0x790  ldarg.0
0x791  call     instance void [mscorlib]System.Object::.ctor()
0x796  ldarg.1
0x797  ldarg.0
0x798  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusPlugin::entityId
0x79d  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x7a2  brtrue.s loc_7AF
0x7a4  ldstr    aInputConfigura// "Input configuration should be a guid."
0x7a9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x7ae  throw
0x7af  ret
```
