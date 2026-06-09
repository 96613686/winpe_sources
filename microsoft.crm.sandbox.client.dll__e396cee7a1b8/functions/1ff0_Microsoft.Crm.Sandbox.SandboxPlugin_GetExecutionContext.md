# Microsoft.Crm.Sandbox.SandboxPlugin::GetExecutionContext

- ea: `0x1ff0`
- end: `0x2006`
- name: `Microsoft.Crm.Sandbox.SandboxPlugin::GetExecutionContext`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2080`

## pseudocode

```c

```

## disassembly

```asm
0x1ff0  ldarg.1
0x1ff1  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x1ff6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ffb  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x2000  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x2005  ret
```
