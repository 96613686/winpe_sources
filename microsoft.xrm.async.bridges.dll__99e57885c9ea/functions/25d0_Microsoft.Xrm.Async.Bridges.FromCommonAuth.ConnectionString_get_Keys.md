# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::get_Keys

- ea: `0x25d0`
- end: `0x25e1`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::get_Keys`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x25d0  ldarg.0
0x25d1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::properties
0x25d6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x25db  call     T0x2B000069
0x25e0  ret
```
