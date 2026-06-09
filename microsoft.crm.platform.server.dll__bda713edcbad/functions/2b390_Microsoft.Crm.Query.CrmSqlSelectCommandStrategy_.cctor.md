# Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::.cctor

- ea: `0x2b390`
- end: `0x2b3db`
- name: `Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::.cctor`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x2b3c1`: `Total Select From Extension Table`
- `0x2b3c6`: `Total Select From Extension Table`

## pseudocode

```c

```

## disassembly

```asm
0x2b390  ldc.i4.3
0x2b391  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter>::.ctor(int32)
0x2b396  dup
0x2b397  ldstr    aTotalSelectFro// "Total Select From View"
0x2b39c  ldstr    aTotalSelectFro// "Total Select From View"
0x2b3a1  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterFactory::GetCounter(string)
0x2b3a6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter>::Add(var<u1>, !!T0)
0x2b3ab  dup
0x2b3ac  ldstr    aTotalSelectFro_0// "Total Select From Base Table"
0x2b3b1  ldstr    aTotalSelectFro_0// "Total Select From Base Table"
0x2b3b6  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterFactory::GetCounter(string)
0x2b3bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter>::Add(var<u1>, !!T0)
0x2b3c0  dup
0x2b3c1  ldstr    aTotalSelectFro_1// "Total Select From Extension Table"
0x2b3c6  ldstr    aTotalSelectFro_1// "Total Select From Extension Table"
0x2b3cb  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterFactory::GetCounter(string)
0x2b3d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter>::Add(var<u1>, !!T0)
0x2b3d5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter> Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::PerformanceCounters
0x2b3da  ret
```
