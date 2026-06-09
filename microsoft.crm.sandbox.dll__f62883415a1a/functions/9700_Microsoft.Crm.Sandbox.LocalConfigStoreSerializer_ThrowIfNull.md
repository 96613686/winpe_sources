# Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ThrowIfNull

- ea: `0x9700`
- end: `0x970b`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ThrowIfNull`
- size: `11`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x94f0`
- `0x9540`
- `0x9560`
- `0x9580`

## callees

- `0x9700`

## pseudocode

```c

```

## disassembly

```asm
0x9700  ldarg.1
0x9701  brtrue.s loc_970A
0x9703  ldarg.2
0x9704  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9709  throw
0x970a  ret
```
