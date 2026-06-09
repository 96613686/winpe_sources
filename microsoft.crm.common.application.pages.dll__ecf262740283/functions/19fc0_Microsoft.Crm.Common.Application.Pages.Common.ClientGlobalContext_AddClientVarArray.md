# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVarArray

- ea: `0x19fc0`
- end: `0x1a042`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVarArray`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a050`

## callees

- `0x19f80`
- `0x19fc0`

## pseudocode

```c

```

## disassembly

```asm
0x19fc0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x19fc5  stloc.0
0x19fc6  ldloc.0
0x19fc7  ldstr    asc_33842// "["
0x19fcc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x19fd1  pop
0x19fd2  ldc.i4.0
0x19fd3  stloc.1
0x19fd4  ldarg.3
0x19fd5  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x19fda  stloc.2
0x19fdb  br.s     loc_1A009
0x19fdd  ldloc.2
0x19fde  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19fe3  stloc.3
0x19fe4  ldloc.1
0x19fe5  brtrue.s loc_19FEB
0x19fe7  ldc.i4.1
0x19fe8  stloc.1
0x19fe9  br.s     loc_19FF7
0x19feb  ldloc.0
0x19fec  ldstr    asc_25960// ", "
0x19ff1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x19ff6  pop
0x19ff7  ldloc.0
0x19ff8  ldloc.3
0x19ff9  callvirt instance string [mscorlib]System.Object::ToString()
0x19ffe  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1a003  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a008  pop
0x1a009  ldloc.2
0x1a00a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a00f  brtrue.s loc_19FDD
0x1a011  leave.s  loc_1A027
0x1a013  ldloc.2
0x1a014  isinst   [mscorlib]System.IDisposable
0x1a019  stloc.s  4
0x1a01b  ldloc.s  4
0x1a01d  brfalse.s loc_1A026
0x1a01f  ldloc.s  4
0x1a021  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a026  endfinally
0x1a027  ldloc.0
0x1a028  ldstr    asc_25A1C// "]"
0x1a02d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a032  pop
0x1a033  ldarg.0
0x1a034  ldarg.1
0x1a035  ldarg.2
0x1a036  ldloc.0
0x1a037  callvirt instance string [mscorlib]System.Object::ToString()
0x1a03c  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVarInternal(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a041  ret
```
