# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetClickableSubjectForRefTokens

- ea: `0x11410`
- end: `0x1144e`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetClickableSubjectForRefTokens`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x11390`

## callees

- `0x12d60`
- `0x12de0`

## pseudocode

```c

```

## disassembly

```asm
0x11410  ldarg.1
0x11411  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ActivityId()
0x11416  stloc.2
0x11417  ldloca.s 2
0x11419  constrained. [mscorlib]System.Guid
0x1141f  callvirt instance string [mscorlib]System.Object::ToString()
0x11424  stloc.0
0x11425  ldarg.1
0x11426  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_Subject()
0x1142b  stloc.1
0x1142c  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::.ctor()
0x11431  dup
0x11432  ldloc.0
0x11433  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Id(string)
0x11438  dup
0x11439  ldloc.1
0x1143a  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Name(string)
0x1143f  dup
0x11440  ldarg.2
0x11441  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_TypeCode(int32)
0x11446  dup
0x11447  ldc.i4.2
0x11448  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Type(valuetype [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ParamType)
0x1144d  ret
```
