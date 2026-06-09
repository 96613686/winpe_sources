# Microsoft.Crm.Controls.Footer::GetInitControlsJsBlock

- ea: `0x9140`
- end: `0x919c`
- name: `Microsoft.Crm.Controls.Footer::GetInitControlsJsBlock`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x91a0`

## callees

- `0x22a0`
- `0x9140`

## string_xrefs

- `0x9147`: `Sys.Application.beginCreateComponents();`
- `0x918a`: `Sys.Application.endCreateComponents();`

## pseudocode

```c

```

## disassembly

```asm
0x9140  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x9145  stloc.0
0x9146  ldloc.0
0x9147  ldstr    aSysApplication_0// "Sys.Application.beginCreateComponents()"...
0x914c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x9151  pop
0x9152  ldarg.0
0x9153  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Controls.PageResourceManager::get_ApplicationInitStatementsList()
0x9158  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x915d  stloc.1
0x915e  br.s     loc_9170
0x9160  ldloca.s 1
0x9162  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x9167  stloc.2
0x9168  ldloc.0
0x9169  ldloc.2
0x916a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x916f  pop
0x9170  ldloca.s 1
0x9172  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x9177  brtrue.s loc_9160
0x9179  leave.s  loc_9189
0x917b  ldloca.s 1
0x917d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x9183  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9188  endfinally
0x9189  ldloc.0
0x918a  ldstr    aSysApplication_3// "Sys.Application.endCreateComponents();"
0x918f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x9194  pop
0x9195  ldloc.0
0x9196  callvirt instance string [mscorlib]System.Object::ToString()
0x919b  ret
```
