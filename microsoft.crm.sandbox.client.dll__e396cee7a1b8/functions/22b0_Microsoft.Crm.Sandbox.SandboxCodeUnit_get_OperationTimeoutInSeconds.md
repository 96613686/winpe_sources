# Microsoft.Crm.Sandbox.SandboxCodeUnit::get_OperationTimeoutInSeconds

- ea: `0x22b0`
- end: `0x22ca`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::get_OperationTimeoutInSeconds`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x17f0`
- `0x2f70`

## callees

- `0x1a80`
- `0x22b0`

## pseudocode

```c

```

## disassembly

```asm
0x22b0  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientConfiguration Microsoft.Crm.Sandbox.SandboxHostManager::get_ClientConfiguration()
0x22b5  ldc.i4.2
0x22b6  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientProperty)
0x22bb  stloc.0
0x22bc  ldloc.0
0x22bd  ldc.i4.0
0x22be  bgt.s    loc_22C8
0x22c0  ldsfld   int32[] [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyDefaultValues::SandboxClientPropertyDefaults
0x22c5  ldc.i4.2
0x22c6  ldelem.i4
0x22c7  ret
0x22c8  ldloc.0
0x22c9  ret
```
