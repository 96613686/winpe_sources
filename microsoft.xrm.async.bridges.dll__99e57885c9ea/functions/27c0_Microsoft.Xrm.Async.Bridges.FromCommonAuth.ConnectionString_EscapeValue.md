# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::EscapeValue

- ea: `0x27c0`
- end: `0x2800`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::EscapeValue`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2760`

## callees

- `0x27c0`

## pseudocode

```c

```

## disassembly

```asm
0x27c0  ldarg.0
0x27c1  ldc.i4.s 0x22
0x27c3  call     T0x2B00006B
0x27c8  brfalse.s loc_27E8
0x27ca  ldarg.0
0x27cb  ldstr    asc_56A2// "\""
0x27d0  ldstr    asc_56A6// "\\\""
0x27d5  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x27da  starg.s  0
0x27dc  ldstr    a0// "\"{0}\""
0x27e1  ldarg.0
0x27e2  call     string [mscorlib]System.String::Format(string, object)
0x27e7  ret
0x27e8  ldarg.0
0x27e9  ldc.i4.s 0x27
0x27eb  call     T0x2B00006B
0x27f0  brfalse.s loc_27FE
0x27f2  ldstr    a0// "\"{0}\""
0x27f7  ldarg.0
0x27f8  call     string [mscorlib]System.String::Format(string, object)
0x27fd  ret
0x27fe  ldarg.0
0x27ff  ret
```
