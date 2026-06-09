# Microsoft.Crm.Sandbox.InternalSandboxSdkClient::remove_ServerError

- ea: `0x150`
- end: `0x179`
- name: `Microsoft.Crm.Sandbox.InternalSandboxSdkClient::remove_ServerError`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x150`

## pseudocode

```c

```

## disassembly

```asm
0x150  ldarg.0
0x151  ldfld    class [mscorlib]System.EventHandler`1<class Microsoft.Crm.Sandbox.ServerErrorEventArgs> Microsoft.Crm.Sandbox.InternalSandboxSdkClient::ServerError
0x156  stloc.0
0x157  ldloc.0
0x158  stloc.1
0x159  ldloc.1
0x15a  ldarg.1
0x15b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x160  castclass class [mscorlib]System.EventHandler`1<class Microsoft.Crm.Sandbox.ServerErrorEventArgs>
0x165  stloc.2
0x166  ldarg.0
0x167  ldflda   class [mscorlib]System.EventHandler`1<class Microsoft.Crm.Sandbox.ServerErrorEventArgs> Microsoft.Crm.Sandbox.InternalSandboxSdkClient::ServerError
0x16c  ldloc.2
0x16d  ldloc.1
0x16e  call     T0x2B000001
0x173  stloc.0
0x174  ldloc.0
0x175  ldloc.1
0x176  bne.un.s loc_157
0x178  ret
```
