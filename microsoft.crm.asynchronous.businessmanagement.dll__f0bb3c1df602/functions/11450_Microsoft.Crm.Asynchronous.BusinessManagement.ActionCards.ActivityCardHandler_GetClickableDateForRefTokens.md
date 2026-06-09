# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetClickableDateForRefTokens

- ea: `0x11450`
- end: `0x114a8`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetClickableDateForRefTokens`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x11390`

## callees

- `0x11450`
- `0x12de0`
- `0x12e60`
- `0x12e80`

## pseudocode

```c

```

## disassembly

```asm
0x11450  ldarg.1
0x11451  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_Subject()
0x11456  stloc.0
0x11457  ldarg.3
0x11458  ldc.i4.s 0x15
0x1145a  bne.un.s loc_11472
0x1145c  ldarg.1
0x1145d  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledStart()
0x11462  stloc.1
0x11463  ldloca.s 1
0x11465  ldstr    aHhMmTt// "hh:mm tt"
0x1146a  call     instance string [mscorlib]System.DateTime::ToString(string)
0x1146f  stloc.0
0x11470  br.s     loc_11486
0x11472  ldarg.1
0x11473  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x11478  stloc.2
0x11479  ldloca.s 2
0x1147b  ldstr    aHhMmTt// "hh:mm tt"
0x11480  call     instance string [mscorlib]System.DateTime::ToString(string)
0x11485  stloc.0
0x11486  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::.ctor()
0x1148b  dup
0x1148c  ldnull
0x1148d  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Id(string)
0x11492  dup
0x11493  ldloc.0
0x11494  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Name(string)
0x11499  dup
0x1149a  ldc.i4.0
0x1149b  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_TypeCode(int32)
0x114a0  dup
0x114a1  ldc.i4.1
0x114a2  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Type(valuetype [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ParamType)
0x114a7  ret
```
