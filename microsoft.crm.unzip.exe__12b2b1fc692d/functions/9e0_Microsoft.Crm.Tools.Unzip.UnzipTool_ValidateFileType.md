# Microsoft.Crm.Tools.Unzip.UnzipTool::ValidateFileType

- ea: `0x9e0`
- end: `0xa1f`
- name: `Microsoft.Crm.Tools.Unzip.UnzipTool::ValidateFileType`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6f0`

## callees

- `0x9e0`

## pseudocode

```c

```

## disassembly

```asm
0x9e0  ldarg.0
0x9e1  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.Unzip.UnzipTool::ValidFileTypes
0x9e6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x9eb  stloc.0
0x9ec  br.s     loc_A02
0x9ee  ldloca.s 0
0x9f0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x9f5  ldarg.1
0x9f6  ldc.i4.5
0x9f7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x9fc  brtrue.s loc_A02
0x9fe  ldc.i4.1
0x9ff  stloc.1
0xa00  leave.s  loc_A1D
0xa02  ldloca.s 0
0xa04  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0xa09  brtrue.s loc_9EE
0xa0b  leave.s  loc_A1B
0xa0d  ldloca.s 0
0xa0f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0xa15  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa1a  endfinally
0xa1b  ldc.i4.0
0xa1c  ret
0xa1d  ldloc.1
0xa1e  ret
```
