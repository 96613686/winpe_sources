# Microsoft.Crm.Workflow.ConditionHandlerString::stringComparation

- ea: `0xca80`
- end: `0xcaba`
- name: `Microsoft.Crm.Workflow.ConditionHandlerString::stringComparation`
- size: `58`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xcac0`
- `0xcad0`
- `0xcae0`
- `0xcaf0`

## callees

- `0xa320`
- `0xa770`
- `0xa7e0`
- `0xca80`

## pseudocode

```c

```

## disassembly

```asm
0xca80  ldarg.0
0xca81  ldarg.2
0xca82  call     instance void Microsoft.Crm.Workflow.ConditionHandlerBase::ValidateBinary(object[] values)
0xca87  ldarg.1
0xca88  isinst   [mscorlib]System.String
0xca8d  ldarg.2
0xca8e  ldc.i4.0
0xca8f  ldelem.ref
0xca90  isinst   [mscorlib]System.String
0xca95  stloc.0
0xca96  dup
0xca97  brfalse.s loc_CA9C
0xca99  ldloc.0
0xca9a  brtrue.s loc_CAA7
0xca9c  ldstr    aIncorrectTypes// "Incorrect types specified"
0xcaa1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xcaa6  throw
0xcaa7  ldloc.0
0xcaa8  ldc.i4.0
0xcaa9  ldarg.0
0xcaaa  call     instance class Microsoft.Crm.Workflow.ConditionContext Microsoft.Crm.Workflow.ConditionHandlerBase::get_ConditionContext()
0xcaaf  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Workflow.ConditionContext::get_CultureInfo()
0xcab4  call     int32 [mscorlib]System.String::Compare(string, string, bool, class [mscorlib]System.Globalization.CultureInfo)
0xcab9  ret
```
