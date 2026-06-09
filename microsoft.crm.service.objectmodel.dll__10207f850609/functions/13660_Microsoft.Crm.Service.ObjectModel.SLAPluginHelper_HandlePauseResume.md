# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HandlePauseResume

- ea: `0x13660`
- end: `0x136bc`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HandlePauseResume`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10900`
- `0x12ca0`

## callees

- `0x131a0`
- `0x132b0`
- `0x13660`

## pseudocode

```c

```

## disassembly

```asm
0x13660  ldsfld   string [mscorlib]System.String::Empty
0x13665  stloc.0
0x13666  ldc.i4.0
0x13667  stloc.1
0x13668  ldc.i4.0
0x13669  stloc.2
0x1366a  ldc.i4.0
0x1366b  newarr   [mscorlib]System.String
0x13670  stloc.3
0x13671  ldarg.2
0x13672  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x13677  call     string Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetSlaPauseStates(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1367c  stloc.0
0x1367d  ldloc.0
0x1367e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13683  brtrue.s loc_13697
0x13685  ldloc.0
0x13686  ldc.i4.1
0x13687  newarr   [mscorlib]System.Char
0x1368c  dup
0x1368d  ldc.i4.0
0x1368e  ldc.i4.s 0x3B
0x13690  stelem.i2
0x13691  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x13696  stloc.3
0x13697  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x1369c  brfalse.s loc_136A1
0x1369e  ldc.i4.0
0x1369f  br.s     loc_136B3
0x136a1  ldloc.3
0x136a2  ldarg.0
0x136a3  ldarg.1
0x136a4  ldarg.2
0x136a5  ldarg.3
0x136a6  ldarg.s  4
0x136a8  ldarg.s  5
0x136aa  ldloca.s 1
0x136ac  ldloca.s 2
0x136ae  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CheckToInvokeSla(string[] arrSlaPauseStates, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext, valuetype [mscorlib]System.Guid primaryEntityId, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident incident, valuetype [mscorlib]System.Guid calenderId, [out] int32& slaKpiStatus, [out] int32& totalCaseOnHoldTime)
0x136b3  ldarg.s  6
0x136b5  ldloc.1
0x136b6  stind.i4
0x136b7  ldarg.s  7
0x136b9  ldloc.2
0x136ba  stind.i4
0x136bb  ret
```
