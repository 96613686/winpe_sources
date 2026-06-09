# Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::GetOpenGraphType

- ea: `0x84a0`
- end: `0x8524`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::GetOpenGraphType`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8370`

## callees

- `0x84a0`

## string_xrefs

- `0x84c5`: `competitor`
- `0x8506`: `competitor`

## pseudocode

```c

```

## disassembly

```asm
0x84a0  ldarg.1
0x84a1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x84a6  brfalse.s loc_84AA
0x84a8  ldnull
0x84a9  ret
0x84aa  ldarg.1
0x84ab  ldstr    aAccount// "account"
0x84b0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84b5  brtrue.s loc_84FA
0x84b7  ldarg.1
0x84b8  ldstr    aIncident// "incident"
0x84bd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84c2  brtrue.s loc_8500
0x84c4  ldarg.1
0x84c5  ldstr    aCompetitor// "competitor"
0x84ca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84cf  brtrue.s loc_8506
0x84d1  ldarg.1
0x84d2  ldstr    aContact// "contact"
0x84d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84dc  brtrue.s loc_850C
0x84de  ldarg.1
0x84df  ldstr    aLead// "lead"
0x84e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84e9  brtrue.s loc_8512
0x84eb  ldarg.1
0x84ec  ldstr    aOpportunity// "opportunity"
0x84f1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84f6  brtrue.s loc_8518
0x84f8  br.s     loc_851E
0x84fa  ldstr    aAccount// "account"
0x84ff  ret
0x8500  ldstr    aCase// "case"
0x8505  ret
0x8506  ldstr    aCompetitor// "competitor"
0x850b  ret
0x850c  ldstr    aContact// "contact"
0x8511  ret
0x8512  ldstr    aLead// "lead"
0x8517  ret
0x8518  ldstr    aOpportunity// "opportunity"
0x851d  ret
0x851e  ldstr    aRecord// "record"
0x8523  ret
```
