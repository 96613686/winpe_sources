# Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::Merge

- ea: `0x6040`
- end: `0x6053`
- name: `Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::Merge`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x6290`

## pseudocode

```c

```

## disassembly

```asm
0x6040  ldarg.1
0x6041  ldstr    aOriginalcontex// "originalContext"
0x6046  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x604b  ldarg.0
0x604c  ldarg.1
0x604d  call     instance void Microsoft.Crm.Sandbox.SandboxExecutionContext::Merge(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext originalContext)
0x6052  ret
```
