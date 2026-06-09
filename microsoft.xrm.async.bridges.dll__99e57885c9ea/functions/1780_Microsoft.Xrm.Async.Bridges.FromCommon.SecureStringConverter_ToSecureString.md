# Microsoft.Xrm.Async.Bridges.FromCommon.SecureStringConverter::ToSecureString

- ea: `0x1780`
- end: `0x17bf`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.SecureStringConverter::ToSecureString`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xab0`
- `0x1780`

## pseudocode

```c

```

## disassembly

```asm
0x1780  ldarg.1
0x1781  ldstr    aItem// "item"
0x1786  call     T0x2B000024
0x178b  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x1790  pop
0x1791  newobj   instance void [mscorlib]System.Security.SecureString::.ctor()
0x1796  stloc.0
0x1797  ldarg.1
0x1798  callvirt instance char[] [mscorlib]System.String::ToCharArray()
0x179d  stloc.1
0x179e  ldc.i4.0
0x179f  stloc.2
0x17a0  br.s     loc_17B1
0x17a2  ldloc.1
0x17a3  ldloc.2
0x17a4  ldelem.u2
0x17a5  stloc.3
0x17a6  ldloc.0
0x17a7  ldloc.3
0x17a8  callvirt instance void [mscorlib]System.Security.SecureString::AppendChar(char)
0x17ad  ldloc.2
0x17ae  ldc.i4.1
0x17af  add
0x17b0  stloc.2
0x17b1  ldloc.2
0x17b2  ldloc.1
0x17b3  ldlen
0x17b4  conv.i4
0x17b5  blt.s    loc_17A2
0x17b7  ldloc.0
0x17b8  callvirt instance void [mscorlib]System.Security.SecureString::MakeReadOnly()
0x17bd  ldloc.0
0x17be  ret
```
