# Microsoft.Crm.Sandbox.InternalSandboxSdkClient::add_ExecuteComplete

- ea: `0x180`
- end: `0x1a9`
- name: `Microsoft.Crm.Sandbox.InternalSandboxSdkClient::add_ExecuteComplete`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xaeb0`

## callees

- `0x180`

## pseudocode

```c

```

## disassembly

```asm
0x180  ldarg.0
0x181  ldfld    class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs> Microsoft.Crm.Sandbox.InternalSandboxSdkClient::ExecuteComplete
0x186  stloc.0
0x187  ldloc.0
0x188  stloc.1
0x189  ldloc.1
0x18a  ldarg.1
0x18b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x190  castclass class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs>
0x195  stloc.2
0x196  ldarg.0
0x197  ldflda   class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs> Microsoft.Crm.Sandbox.InternalSandboxSdkClient::ExecuteComplete
0x19c  ldloc.2
0x19d  ldloc.1
0x19e  call     T0x2B000002
0x1a3  stloc.0
0x1a4  ldloc.0
0x1a5  ldloc.1
0x1a6  bne.un.s loc_187
0x1a8  ret
```
