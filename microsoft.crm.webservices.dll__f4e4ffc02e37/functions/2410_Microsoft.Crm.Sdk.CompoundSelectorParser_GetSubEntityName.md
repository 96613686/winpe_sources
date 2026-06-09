# Microsoft.Crm.Sdk.CompoundSelectorParser::GetSubEntityName

- ea: `0x2410`
- end: `0x242f`
- name: `Microsoft.Crm.Sdk.CompoundSelectorParser::GetSubEntityName`
- size: `31`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2130`
- `0x2190`
- `0x22c0`

## callees

- `0x2410`

## pseudocode

```c

```

## disassembly

```asm
0x2410  ldarg.1
0x2411  ldstr    aDuplicaterule// "DuplicateRule"
0x2416  call     bool [mscorlib]System.String::op_Equality(string, string)
0x241b  brfalse.s loc_2423
0x241d  ldstr    aDuplicaterulec// "DuplicateRuleCondition"
0x2422  ret
0x2423  ldarg.1
0x2424  ldstr    aDetail// "Detail"
0x2429  call     string [mscorlib]System.String::Concat(string, string)
0x242e  ret
```
