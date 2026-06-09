# Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::GetNextArticleProcessingTime

- ea: `0xaec0`
- end: `0xaf13`
- name: `Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::GetNextArticleProcessingTime`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa7b0`

## callees

- `0xaea0`
- `0xaec0`
- `0xaf20`
- `0xb030`

## pseudocode

```c

```

## disassembly

```asm
0xaec0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xaec5  stloc.2
0xaec6  ldloca.s 2
0xaec8  ldc.r8   1.0
0xaed1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xaed6  stloc.0
0xaed7  ldarg.0
0xaed8  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_now
0xaedd  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0xaee2  stloc.1
0xaee3  ldarg.0
0xaee4  call     instance bool Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::HasJobBeenAbortedOrPaused()
0xaee9  brtrue.s loc_AF11
0xaeeb  ldarg.0
0xaeec  ldloc.0
0xaeed  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::GetNearestExpiringKnowledgeArticleTime(valuetype [mscorlib]System.DateTime minTime)
0xaef2  stloc.3
0xaef3  ldarg.0
0xaef4  ldloc.0
0xaef5  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::GetNearestKnowledgeArticlePublishTime(valuetype [mscorlib]System.DateTime minTime)
0xaefa  stloc.s  4
0xaefc  ldloc.3
0xaefd  ldloc.s  4
0xaeff  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xaf04  brtrue.s loc_AF0A
0xaf06  ldloc.s  4
0xaf08  br.s     loc_AF0B
0xaf0a  ldloc.3
0xaf0b  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0xaf10  stloc.1
0xaf11  ldloc.1
0xaf12  ret
```
