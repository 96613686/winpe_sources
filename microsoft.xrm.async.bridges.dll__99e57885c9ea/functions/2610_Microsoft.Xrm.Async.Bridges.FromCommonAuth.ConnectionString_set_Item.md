# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::set_Item

- ea: `0x2610`
- end: `0x261e`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::set_Item`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2610  ldarg.0
0x2611  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::properties
0x2616  ldarg.1
0x2617  ldarg.2
0x2618  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x261d  ret
```
