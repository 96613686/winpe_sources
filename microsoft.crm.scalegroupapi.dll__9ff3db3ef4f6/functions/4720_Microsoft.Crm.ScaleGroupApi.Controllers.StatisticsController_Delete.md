# Microsoft.Crm.ScaleGroupApi.Controllers.StatisticsController::Delete

- ea: `0x4720`
- end: `0x473c`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.StatisticsController::Delete`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x4720`

## pseudocode

```c

```

## disassembly

```asm
0x4720  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x4725  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x472a  stloc.0
0x472b  ldloc.0
0x472c  ldarg.1
0x472d  call     bool [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::DoesStatisticsExist(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4732  brfalse.s loc_473B
0x4734  ldloc.0
0x4735  ldarg.1
0x4736  call     void [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsAdministrator::DeleteOrganizationFromStatisticsDatabase(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x473b  ret
```
