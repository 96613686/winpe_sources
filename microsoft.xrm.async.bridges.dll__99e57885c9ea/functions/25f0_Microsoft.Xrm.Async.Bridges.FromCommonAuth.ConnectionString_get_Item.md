# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::get_Item

- ea: `0x25f0`
- end: `0x2601`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::get_Item`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2340`
- `0x2870`

## pseudocode

```c

```

## disassembly

```asm
0x25f0  ldarg.0
0x25f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::properties
0x25f6  ldarg.1
0x25f7  ldloca.s 0
0x25f9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x25fe  pop
0x25ff  ldloc.0
0x2600  ret
```
