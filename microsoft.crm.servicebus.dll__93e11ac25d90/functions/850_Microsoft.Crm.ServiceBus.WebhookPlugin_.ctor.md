# Microsoft.Crm.ServiceBus.WebhookPlugin::.ctor

- ea: `0x850`
- end: `0x870`
- name: `Microsoft.Crm.ServiceBus.WebhookPlugin::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x850`

## string_xrefs

- `0x864`: `Input configuration should be a guid.`

## pseudocode

```c

```

## disassembly

```asm
0x850  ldarg.0
0x851  call     instance void [mscorlib]System.Object::.ctor()
0x856  ldarg.1
0x857  ldarg.0
0x858  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.WebhookPlugin::entityId
0x85d  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x862  brtrue.s loc_86F
0x864  ldstr    aInputConfigura// "Input configuration should be a guid."
0x869  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x86e  throw
0x86f  ret
```
