# Microsoft.Crm.Sdk.ServiceDescription::ReplaceTokens

- ea: `0x8740`
- end: `0x876c`
- name: `Microsoft.Crm.Sdk.ServiceDescription::ReplaceTokens`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8e90`

## callees

- `0x8740`

## pseudocode

```c

```

## disassembly

```asm
0x8740  ldarg.0
0x8741  ldlen
0x8742  brfalse.s loc_8754
0x8744  ldarg.1
0x8745  ldstr    aEntityPrimarye// "{Entity.PrimaryEntityName}"
0x874a  ldarg.0
0x874b  ldc.i4.0
0x874c  ldelem.ref
0x874d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8752  starg.s  1
0x8754  ldarg.0
0x8755  ldlen
0x8756  conv.i4
0x8757  ldc.i4.2
0x8758  bne.un.s loc_876A
0x875a  ldarg.1
0x875b  ldstr    aEntitySecondar// "{Entity.SecondaryEntityName}"
0x8760  ldarg.0
0x8761  ldc.i4.1
0x8762  ldelem.ref
0x8763  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8768  starg.s  1
0x876a  ldarg.1
0x876b  ret
```
