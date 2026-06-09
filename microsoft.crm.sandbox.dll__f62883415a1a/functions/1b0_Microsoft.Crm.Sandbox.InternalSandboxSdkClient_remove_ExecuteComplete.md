# Microsoft.Crm.Sandbox.InternalSandboxSdkClient::remove_ExecuteComplete

- ea: `0x1b0`
- end: `0x1d9`
- name: `Microsoft.Crm.Sandbox.InternalSandboxSdkClient::remove_ExecuteComplete`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1b0`

## pseudocode

```c

```

## disassembly

```asm
0x1b0  ldarg.0
0x1b1  ldfld    class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs> Microsoft.Crm.Sandbox.InternalSandboxSdkClient::ExecuteComplete
0x1b6  stloc.0
0x1b7  ldloc.0
0x1b8  stloc.1
0x1b9  ldloc.1
0x1ba  ldarg.1
0x1bb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x1c0  castclass class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs>
0x1c5  stloc.2
0x1c6  ldarg.0
0x1c7  ldflda   class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs> Microsoft.Crm.Sandbox.InternalSandboxSdkClient::ExecuteComplete
0x1cc  ldloc.2
0x1cd  ldloc.1
0x1ce  call     T0x2B000002
0x1d3  stloc.0
0x1d4  ldloc.0
0x1d5  ldloc.1
0x1d6  bne.un.s loc_1B7
0x1d8  ret
```
