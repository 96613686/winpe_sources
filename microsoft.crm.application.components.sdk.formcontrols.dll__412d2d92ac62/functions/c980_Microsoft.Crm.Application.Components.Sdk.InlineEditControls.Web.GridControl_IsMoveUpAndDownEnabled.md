# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsMoveUpAndDownEnabled

- ea: `0xc980`
- end: `0xca8b`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsMoveUpAndDownEnabled`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xc7d0`

## callees

- `0xbca0`
- `0xc980`
- `0x2cb60`

## string_xrefs

- `0xca30`: `channelaccessprofilerule`

## pseudocode

```c

```

## disassembly

```asm
0xc980  ldarg.0
0xc981  callvirt instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::get_CurrentEntityName()
0xc986  stloc.0
0xc987  ldloc.0
0xc988  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xc98d  stloc.1
0xc98e  ldloc.1
0xc98f  ldc.i4   0x6C897E3D
0xc994  bgt.un.s loc_C9C8
0xc996  ldloc.1
0xc997  ldc.i4   0x5A906110
0xc99c  bgt.un.s loc_C9B3
0xc99e  ldloc.1
0xc99f  ldc.i4   0x391C1186
0xc9a4  beq.s    loc_CA02
0xc9a6  ldloc.1
0xc9a7  ldc.i4   0x5A906110
0xc9ac  beq.s    loc_CA11
0xc9ae  br       loc_CA89
0xc9b3  ldloc.1
0xc9b4  ldc.i4   0x6BE5AA1A
0xc9b9  beq.s    loc_CA20
0xc9bb  ldloc.1
0xc9bc  ldc.i4   0x6C897E3D
0xc9c1  beq.s    loc_CA2F
0xc9c3  br       loc_CA89
0xc9c8  ldloc.1
0xc9c9  ldc.i4   0x98689BE9
0xc9ce  bgt.un.s loc_C9E5
0xc9d0  ldloc.1
0xc9d1  ldc.i4   0x733C356F
0xc9d6  beq.s    loc_CA4D
0xc9d8  ldloc.1
0xc9d9  ldc.i4   0x98689BE9
0xc9de  beq.s    loc_CA5C
0xc9e0  br       loc_CA89
0xc9e5  ldloc.1
0xc9e6  ldc.i4   0xB2887BD7
0xc9eb  beq.s    loc_CA3E
0xc9ed  ldloc.1
0xc9ee  ldc.i4   0xC5384E91
0xc9f3  beq.s    loc_CA6B
0xc9f5  ldloc.1
0xc9f6  ldc.i4   0xCF2F4271
0xc9fb  beq.s    loc_CA7A
0xc9fd  br       loc_CA89
0xca02  ldloc.0
0xca03  ldstr    aConvertrule// "convertrule"
0xca08  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca0d  brtrue.s loc_CA87
0xca0f  br.s     loc_CA89
0xca11  ldloc.0
0xca12  ldstr    aInvoice// "invoice"
0xca17  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca1c  brtrue.s loc_CA87
0xca1e  br.s     loc_CA89
0xca20  ldloc.0
0xca21  ldstr    aOpportunity// "opportunity"
0xca26  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca2b  brtrue.s loc_CA87
0xca2d  br.s     loc_CA89
0xca2f  ldloc.0
0xca30  ldstr    aChannelaccessp// "channelaccessprofilerule"
0xca35  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca3a  brtrue.s loc_CA87
0xca3c  br.s     loc_CA89
0xca3e  ldloc.0
0xca3f  ldstr    aQuote// "quote"
0xca44  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca49  brtrue.s loc_CA87
0xca4b  br.s     loc_CA89
0xca4d  ldloc.0
0xca4e  ldstr    aRoutingrule// "routingrule"
0xca53  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca58  brtrue.s loc_CA87
0xca5a  br.s     loc_CA89
0xca5c  ldloc.0
0xca5d  ldstr    aSalesorder// "salesorder"
0xca62  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca67  brtrue.s loc_CA87
0xca69  br.s     loc_CA89
0xca6b  ldloc.0
0xca6c  ldstr    aSla// "sla"
0xca71  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca76  brtrue.s loc_CA87
0xca78  br.s     loc_CA89
0xca7a  ldloc.0
0xca7b  ldstr    aCategory// "category"
0xca80  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca85  brfalse.s loc_CA89
0xca87  ldc.i4.1
0xca88  ret
0xca89  ldc.i4.0
0xca8a  ret
```
