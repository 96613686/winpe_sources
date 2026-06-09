# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::ToString

- ea: `0x2760`
- end: `0x27bd`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::ToString`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2760`
- `0x27c0`

## pseudocode

```c

```

## disassembly

```asm
0x2760  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2765  stloc.0
0x2766  ldarg.0
0x2767  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::properties
0x276c  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x2771  stloc.1
0x2772  br.s     loc_279D
0x2774  ldloca.s 1
0x2776  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x277b  stloc.2
0x277c  ldloca.s 2
0x277e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x2783  call     string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::EscapeValue(string value)
0x2788  stloc.3
0x2789  ldloc.0
0x278a  ldstr    a01_0// "{0}={1};"
0x278f  ldloca.s 2
0x2791  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x2796  ldloc.3
0x2797  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x279c  pop
0x279d  ldloca.s 1
0x279f  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x27a4  brtrue.s loc_2774
0x27a6  leave.s  loc_27B6
0x27a8  ldloca.s 1
0x27aa  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x27b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27b5  endfinally
0x27b6  ldloc.0
0x27b7  callvirt instance string [mscorlib]System.Object::ToString()
0x27bc  ret
```
