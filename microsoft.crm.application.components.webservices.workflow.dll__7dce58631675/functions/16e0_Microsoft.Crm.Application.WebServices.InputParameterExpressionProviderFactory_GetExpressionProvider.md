# Microsoft.Crm.Application.WebServices.InputParameterExpressionProviderFactory::GetExpressionProvider

- ea: `0x16e0`
- end: `0x171d`
- name: `Microsoft.Crm.Application.WebServices.InputParameterExpressionProviderFactory::GetExpressionProvider`
- size: `61`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xc10`
- `0xc30`
- `0xc60`
- `0xdc0`
- `0xe40`
- `0xfb0`

## callees

- `0x1530`
- `0x1580`
- `0x15d0`
- `0x16e0`

## pseudocode

```c

```

## disassembly

```asm
0x16e0  ldarg.0
0x16e1  ldstr    aCaseorigin// "caseorigin"
0x16e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16eb  brtrue.s loc_1709
0x16ed  ldarg.0
0x16ee  ldstr    aResolvedsender// "ResolvedSenderReference"
0x16f3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16f8  brtrue.s loc_170F
0x16fa  ldarg.0
0x16fb  ldstr    aResolvedsender_0// "ResolvedSenderContactReference"
0x1700  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1705  brtrue.s loc_1715
0x1707  br.s     loc_171B
0x1709  newobj   instance void Microsoft.Crm.Application.WebServices.CaseOriginExpressionProvider::.ctor()
0x170e  ret
0x170f  newobj   instance void Microsoft.Crm.Application.WebServices.ResolvedSenderReferenceExpressionProvider::.ctor()
0x1714  ret
0x1715  newobj   instance void Microsoft.Crm.Application.WebServices.ResolvedSenderContactReferenceExpressionProvider::.ctor()
0x171a  ret
0x171b  ldnull
0x171c  ret
```
