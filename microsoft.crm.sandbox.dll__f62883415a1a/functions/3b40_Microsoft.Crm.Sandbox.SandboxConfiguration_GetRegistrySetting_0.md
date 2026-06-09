# Microsoft.Crm.Sandbox.SandboxConfiguration::GetRegistrySetting_0

- ea: `0x3b40`
- end: `0x3b5d`
- name: `Microsoft.Crm.Sandbox.SandboxConfiguration::GetRegistrySetting_0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3b40`

## pseudocode

```c

```

## disassembly

```asm
0x3b40  ldarg.1
0x3b41  stloc.0
0x3b42  ldarg.0
0x3b43  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x3b48  stloc.1
0x3b49  ldloc.1
0x3b4a  brfalse.s loc_3B5B
0x3b4c  ldloc.1
0x3b4d  isinst   mvar<u1>
0x3b52  brfalse.s loc_3B5B
0x3b54  ldloc.1
0x3b55  unbox.any mvar<u1>
0x3b5a  stloc.0
0x3b5b  ldloc.0
0x3b5c  ret
```
