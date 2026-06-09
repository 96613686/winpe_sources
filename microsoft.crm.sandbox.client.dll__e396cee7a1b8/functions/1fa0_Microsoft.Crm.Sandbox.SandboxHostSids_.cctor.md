# Microsoft.Crm.Sandbox.SandboxHostSids::.cctor

- ea: `0x1fa0`
- end: `0x1fb5`
- name: `Microsoft.Crm.Sandbox.SandboxHostSids::.cctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1fa0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry>::.ctor()
0x1fa5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry> Microsoft.Crm.Sandbox.SandboxHostSids::_sids
0x1faa  newobj   instance void [mscorlib]System.Object::.ctor()
0x1faf  stsfld   object Microsoft.Crm.Sandbox.SandboxHostSids::_lockObject
0x1fb4  ret
```
