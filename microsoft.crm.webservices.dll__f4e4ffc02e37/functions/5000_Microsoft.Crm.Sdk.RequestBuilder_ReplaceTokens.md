# Microsoft.Crm.Sdk.RequestBuilder::ReplaceTokens

- ea: `0x5000`
- end: `0x502c`
- name: `Microsoft.Crm.Sdk.RequestBuilder::ReplaceTokens`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4c50`
- `0x4f30`

## callees

- `0x5000`

## pseudocode

```c

```

## disassembly

```asm
0x5000  ldarg.0
0x5001  ldlen
0x5002  brfalse.s loc_5014
0x5004  ldarg.1
0x5005  ldstr    aEntityPrimarye// "{Entity.PrimaryEntityName}"
0x500a  ldarg.0
0x500b  ldc.i4.0
0x500c  ldelem.ref
0x500d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x5012  starg.s  1
0x5014  ldarg.0
0x5015  ldlen
0x5016  conv.i4
0x5017  ldc.i4.2
0x5018  bne.un.s loc_502A
0x501a  ldarg.1
0x501b  ldstr    aEntitySecondar// "{Entity.SecondaryEntityName}"
0x5020  ldarg.0
0x5021  ldc.i4.1
0x5022  ldelem.ref
0x5023  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x5028  starg.s  1
0x502a  ldarg.1
0x502b  ret
```
