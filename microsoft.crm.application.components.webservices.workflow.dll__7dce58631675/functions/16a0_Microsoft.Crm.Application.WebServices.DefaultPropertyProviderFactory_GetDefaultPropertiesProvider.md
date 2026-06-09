# Microsoft.Crm.Application.WebServices.DefaultPropertyProviderFactory::GetDefaultPropertiesProvider

- ea: `0x16a0`
- end: `0x16be`
- name: `Microsoft.Crm.Application.WebServices.DefaultPropertyProviderFactory::GetDefaultPropertiesProvider`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x8a30`

## callees

- `0xab0`
- `0x1680`
- `0x16a0`

## pseudocode

```c

```

## disassembly

```asm
0x16a0  ldarg.1
0x16a1  ldloca.s 0
0x16a3  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x16a8  brfalse.s loc_16B8
0x16aa  ldloc.0
0x16ab  ldc.i4   0x2455
0x16b0  bne.un.s loc_16B8
0x16b2  newobj   instance void Microsoft.Crm.Application.WebServices.ConvertRuleDefaultPropertiesProvider::.ctor()
0x16b7  ret
0x16b8  newobj   instance void Microsoft.Crm.Application.WebServices.DefaultDefaultPropertiesProvider::.ctor()
0x16bd  ret
```
