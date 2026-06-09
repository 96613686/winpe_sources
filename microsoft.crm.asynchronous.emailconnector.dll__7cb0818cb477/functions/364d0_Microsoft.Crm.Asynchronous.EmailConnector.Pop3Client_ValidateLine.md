# Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::ValidateLine

- ea: `0x364d0`
- end: `0x36522`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::ValidateLine`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x36450`

## callees

- `0x364d0`

## string_xrefs

- `0x364d4`: `command cannot be null`
- `0x3651a`: `<Command removed for security reasons>`

## pseudocode

```c

```

## disassembly

```asm
0x364d0  ldarg.2
0x364d1  ldnull
0x364d2  cgt.un
0x364d4  ldstr    aCommandCannotB// "command cannot be null"
0x364d9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x364de  ldarg.1
0x364df  brtrue.s loc_364E8
0x364e1  ldsfld   string [mscorlib]System.String::Empty
0x364e6  starg.s  1
0x364e8  ldarg.1
0x364e9  ldstr    aOk// "+OK"
0x364ee  ldc.i4.5
0x364ef  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x364f4  brtrue.s loc_36504
0x364f6  ldarg.1
0x364f7  ldstr    aOk_0// "+ OK"
0x364fc  ldc.i4.5
0x364fd  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x36502  brfalse.s loc_36505
0x36504  ret
0x36505  ldarg.3
0x36506  brfalse.s loc_36517
0x36508  ldarg.1
0x36509  ldstr    asc_8DEFE// "+"
0x3650e  ldc.i4.5
0x3650f  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x36514  brfalse.s loc_36517
0x36516  ret
0x36517  ldarg.3
0x36518  brfalse.s loc_36521
0x3651a  ldstr    aCommandRemoved// "<Command removed for security reasons>"
0x3651f  starg.s  2
0x36521  ret
```
