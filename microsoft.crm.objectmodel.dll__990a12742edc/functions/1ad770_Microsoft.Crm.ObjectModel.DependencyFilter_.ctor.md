# Microsoft.Crm.ObjectModel.DependencyFilter::.ctor

- ea: `0x1ad770`
- end: `0x1ad833`
- name: `Microsoft.Crm.ObjectModel.DependencyFilter::.ctor`
- size: `195`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x16c840`
- `0x1932c0`
- `0x1934b0`
- `0x19a270`
- `0x19a2f0`
- `0x19a370`
- `0x19a3a0`
- `0x19a430`
- `0x19a4d0`

## string_xrefs

- `0x1ad80d`: `componenttype`
- `0x1ad779`: `requiredcomponentobjectid`
- `0x1ad7f9`: `requiredcomponentobjectid`
- `0x1ad789`: `requiredcomponenttype`
- `0x1ad7dd`: `requiredcomponenttype`
- `0x1ad781`: `dependentcomponentobjectid`
- `0x1ad7f1`: `dependentcomponentobjectid`
- `0x1ad791`: `dependentcomponenttype`
- `0x1ad7d5`: `dependentcomponenttype`
- `0x1ad7b1`: `dependentcomponentbasesolutionid`
- `0x1ad7a1`: `dependentcomponentparentid`
- `0x1ad799`: `requiredcomponentparentid`
- `0x1ad7a9`: `requiredcomponentbasesolutionid`

## pseudocode

```c

```

## disassembly

```asm
0x1ad770  ldarg.0
0x1ad771  ldc.i4.8
0x1ad772  newarr   [mscorlib]System.String
0x1ad777  dup
0x1ad778  ldc.i4.0
0x1ad779  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x1ad77e  stelem.ref
0x1ad77f  dup
0x1ad780  ldc.i4.1
0x1ad781  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x1ad786  stelem.ref
0x1ad787  dup
0x1ad788  ldc.i4.2
0x1ad789  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x1ad78e  stelem.ref
0x1ad78f  dup
0x1ad790  ldc.i4.3
0x1ad791  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x1ad796  stelem.ref
0x1ad797  dup
0x1ad798  ldc.i4.4
0x1ad799  ldstr    aRequiredcompon_11// "requiredcomponentparentid"
0x1ad79e  stelem.ref
0x1ad79f  dup
0x1ad7a0  ldc.i4.5
0x1ad7a1  ldstr    aDependentcompo_4// "dependentcomponentparentid"
0x1ad7a6  stelem.ref
0x1ad7a7  dup
0x1ad7a8  ldc.i4.6
0x1ad7a9  ldstr    aRequiredcompon_12// "requiredcomponentbasesolutionid"
0x1ad7ae  stelem.ref
0x1ad7af  dup
0x1ad7b0  ldc.i4.7
0x1ad7b1  ldstr    aDependentcompo_3// "dependentcomponentbasesolutionid"
0x1ad7b6  stelem.ref
0x1ad7b7  stfld    string[] Microsoft.Crm.ObjectModel.DependencyFilter::_dependencyFields
0x1ad7bc  ldarg.0
0x1ad7bd  ldstr    aFee29d46B7ce4d// "fee29d46-b7ce-4dc0-97a0-e382afbca7c6"
0x1ad7c2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1ad7c7  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.DependencyFilter::ActivityPartyId
0x1ad7cc  ldarg.0
0x1ad7cd  ldc.i4.2
0x1ad7ce  newarr   [mscorlib]System.String
0x1ad7d3  dup
0x1ad7d4  ldc.i4.0
0x1ad7d5  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x1ad7da  stelem.ref
0x1ad7db  dup
0x1ad7dc  ldc.i4.1
0x1ad7dd  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x1ad7e2  stelem.ref
0x1ad7e3  stfld    string[] Microsoft.Crm.ObjectModel.DependencyFilter::DependencyTypeFields
0x1ad7e8  ldarg.0
0x1ad7e9  ldc.i4.2
0x1ad7ea  newarr   [mscorlib]System.String
0x1ad7ef  dup
0x1ad7f0  ldc.i4.0
0x1ad7f1  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x1ad7f6  stelem.ref
0x1ad7f7  dup
0x1ad7f8  ldc.i4.1
0x1ad7f9  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x1ad7fe  stelem.ref
0x1ad7ff  stfld    string[] Microsoft.Crm.ObjectModel.DependencyFilter::DependencyObjectIdFields
0x1ad804  ldarg.0
0x1ad805  ldc.i4.1
0x1ad806  newarr   [mscorlib]System.String
0x1ad80b  dup
0x1ad80c  ldc.i4.0
0x1ad80d  ldstr    aComponenttype// "componenttype"
0x1ad812  stelem.ref
0x1ad813  stfld    string[] Microsoft.Crm.ObjectModel.DependencyFilter::SolutionComponentTypeFields
0x1ad818  ldarg.0
0x1ad819  ldc.i4.1
0x1ad81a  newarr   [mscorlib]System.String
0x1ad81f  dup
0x1ad820  ldc.i4.0
0x1ad821  ldstr    aObjectid// "objectid"
0x1ad826  stelem.ref
0x1ad827  stfld    string[] Microsoft.Crm.ObjectModel.DependencyFilter::SolutionComponentObjectIdFields
0x1ad82c  ldarg.0
0x1ad82d  call     instance void [mscorlib]System.Object::.ctor()
0x1ad832  ret
```
