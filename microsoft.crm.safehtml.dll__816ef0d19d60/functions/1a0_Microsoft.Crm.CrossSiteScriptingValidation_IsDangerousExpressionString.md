# Microsoft.Crm.CrossSiteScriptingValidation::IsDangerousExpressionString

- ea: `0x1a0`
- end: `0x1e0`
- name: `Microsoft.Crm.CrossSiteScriptingValidation::IsDangerousExpressionString`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1e0`

## callees

- `0x1a0`

## pseudocode

```c

```

## disassembly

```asm
0x1a0  ldarg.1
0x1a1  ldc.i4.s 0xA
0x1a3  add
0x1a4  ldarg.0
0x1a5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1aa  blt.s    loc_1AE
0x1ac  ldc.i4.0
0x1ad  ret
0x1ae  ldarg.0
0x1af  ldarg.1
0x1b0  ldc.i4.1
0x1b1  add
0x1b2  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1b7  ldc.i4.s 0x78
0x1b9  beq.s    loc_1CA
0x1bb  ldarg.0
0x1bc  ldarg.1
0x1bd  ldc.i4.1
0x1be  add
0x1bf  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1c4  ldc.i4.s 0x58
0x1c6  beq.s    loc_1CA
0x1c8  ldc.i4.0
0x1c9  ret
0x1ca  ldarg.0
0x1cb  ldarg.1
0x1cc  ldc.i4.2
0x1cd  add
0x1ce  ldstr    aPression// "pression("
0x1d3  ldc.i4.0
0x1d4  ldc.i4.s 9
0x1d6  ldc.i4.5
0x1d7  call     int32 [mscorlib]System.String::Compare(string, int32, string, int32, int32, valuetype [mscorlib]System.StringComparison)
0x1dc  ldc.i4.0
0x1dd  ceq
0x1df  ret
```
