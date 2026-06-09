# Microsoft.Crm.Metadata.HardCodedEntityExcludedAttributesEvaluator::.ctor

- ea: `0x2b270`
- end: `0x2b33e`
- name: `Microsoft.Crm.Metadata.HardCodedEntityExcludedAttributesEvaluator::.ctor`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2aa80`

## callees

- `0x2ac10`

## string_xrefs

- `0x2b2cc`: `scheduledstart`
- `0x2b2d4`: `scheduledend`
- `0x2b332`: `percentcomplete`

## pseudocode

```c

```

## disassembly

```asm
0x2b270  ldarg.0
0x2b271  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string[]>::.ctor()
0x2b276  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string[]> Microsoft.Crm.Metadata.HardCodedEntityExcludedAttributesEvaluator::_entitiesWithExcludedAttributes
0x2b27b  ldarg.0
0x2b27c  call     instance void Microsoft.Crm.Metadata.CanBeSecuredEvaluator::.ctor()
0x2b281  ldarg.0
0x2b282  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string[]> Microsoft.Crm.Metadata.HardCodedEntityExcludedAttributesEvaluator::_entitiesWithExcludedAttributes
0x2b287  ldstr    a608861bc50a44c// "608861BC-50A4-4C5F-A02C-21FE1943E2CF"
0x2b28c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2b291  ldc.i4.3
0x2b292  newarr   [mscorlib]System.String
0x2b297  dup
0x2b298  ldc.i4.0
0x2b299  ldstr    aSalutation// "salutation"
0x2b29e  stelem.ref
0x2b29f  dup
0x2b2a0  ldc.i4.1
0x2b2a1  ldstr    aSuffix// "suffix"
0x2b2a6  stelem.ref
0x2b2a7  dup
0x2b2a8  ldc.i4.2
0x2b2a9  ldstr    aParentcustomer// "parentcustomerid"
0x2b2ae  stelem.ref
0x2b2af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string[]>::Add(var<u1>, !!T0)
0x2b2b4  ldarg.0
0x2b2b5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string[]> Microsoft.Crm.Metadata.HardCodedEntityExcludedAttributesEvaluator::_entitiesWithExcludedAttributes
0x2b2ba  ldstr    aC821cd41F31543// "C821CD41-F315-43D1-8FA6-82787B6F06E7"
0x2b2bf  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2b2c4  ldc.i4.3
0x2b2c5  newarr   [mscorlib]System.String
0x2b2ca  dup
0x2b2cb  ldc.i4.0
0x2b2cc  ldstr    aScheduledstart// "scheduledstart"
0x2b2d1  stelem.ref
0x2b2d2  dup
0x2b2d3  ldc.i4.1
0x2b2d4  ldstr    aScheduledend// "scheduledend"
0x2b2d9  stelem.ref
0x2b2da  dup
0x2b2db  ldc.i4.2
0x2b2dc  ldstr    aRegardingobjec// "regardingobjectid"
0x2b2e1  stelem.ref
0x2b2e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string[]>::Add(var<u1>, !!T0)
0x2b2e7  ldarg.0
0x2b2e8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string[]> Microsoft.Crm.Metadata.HardCodedEntityExcludedAttributesEvaluator::_entitiesWithExcludedAttributes
0x2b2ed  ldstr    a95ae88b3Cc0c45// "95AE88B3-CC0C-45AC-A2DB-655DCEEC238B"
0x2b2f2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2b2f7  ldc.i4.3
0x2b2f8  newarr   [mscorlib]System.String
0x2b2fd  dup
0x2b2fe  ldc.i4.0
0x2b2ff  ldstr    aTorecipients// "torecipients"
0x2b304  stelem.ref
0x2b305  dup
0x2b306  ldc.i4.1
0x2b307  ldstr    aSender// "sender"
0x2b30c  stelem.ref
0x2b30d  dup
0x2b30e  ldc.i4.2
0x2b30f  ldstr    aNotifications// "notifications"
0x2b314  stelem.ref
0x2b315  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string[]>::Add(var<u1>, !!T0)
0x2b31a  ldarg.0
0x2b31b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string[]> Microsoft.Crm.Metadata.HardCodedEntityExcludedAttributesEvaluator::_entitiesWithExcludedAttributes
0x2b320  ldstr    a78e45d5eF22b4e// "78E45D5E-F22B-4E20-813F-6CD2A3777968"
0x2b325  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2b32a  ldc.i4.1
0x2b32b  newarr   [mscorlib]System.String
0x2b330  dup
0x2b331  ldc.i4.0
0x2b332  ldstr    aPercentcomplet// "percentcomplete"
0x2b337  stelem.ref
0x2b338  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string[]>::Add(var<u1>, !!T0)
0x2b33d  ret
```
