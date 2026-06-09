# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CheckToInvokeSla

- ea: `0x132b0`
- end: `0x133fe`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CheckToInvokeSla`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x13660`

## callees

- `0x132b0`
- `0x13400`
- `0x135b0`
- `0x135c0`
- `0x136c0`
- `0x142e0`
- `0x15180`

## pseudocode

```c

```

## disassembly

```asm
0x132b0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x132b5  stloc.0
0x132b6  ldc.i4.0
0x132b7  stloc.1
0x132b8  ldarg.0
0x132b9  stloc.3
0x132ba  ldc.i4.0
0x132bb  stloc.s  4
0x132bd  br.s     loc_132D3
0x132bf  ldloc.3
0x132c0  ldloc.s  4
0x132c2  ldelem.ref
0x132c3  stloc.s  5
0x132c5  ldloc.0
0x132c6  ldloc.s  5
0x132c8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x132cd  ldloc.s  4
0x132cf  ldc.i4.1
0x132d0  add
0x132d1  stloc.s  4
0x132d3  ldloc.s  4
0x132d5  ldloc.3
0x132d6  ldlen
0x132d7  conv.i4
0x132d8  blt.s    loc_132BF
0x132da  ldarg.s  5
0x132dc  brfalse.s loc_132FE
0x132de  ldarg.s  5
0x132e0  ldstr    aOnholdtime// "onholdtime"
0x132e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x132ea  brfalse.s loc_132FE
0x132ec  ldarg.s  5
0x132ee  ldstr    aOnholdtime// "onholdtime"
0x132f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x132f8  unbox.any [mscorlib]System.Int32
0x132fd  stloc.1
0x132fe  ldloc.0
0x132ff  ldarg.1
0x13300  ldarg.2
0x13301  ldarg.3
0x13302  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x13307  call     valuetype CaseStatusTransition Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::DetermineStatusTransition(class [mscorlib]System.Collections.Generic.List`1<string> slaPauseList, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1330c  stloc.2
0x1330d  ldloc.2
0x1330e  switch   loc_1332C, loc_1332C, loc_1332C, loc_13376, loc_1332C
0x13327  br       loc_133F4
0x1332c  ldarg.s  7
0x1332e  ldc.i4.3
0x1332f  stind.i4
0x13330  ldarg.s  8
0x13332  ldloc.1
0x13333  stind.i4
0x13334  ldloc.2
0x13335  switch   loc_13364, loc_13353, loc_13353, loc_133F4, loc_13364
0x1334e  br       loc_133F4
0x13353  ldarg.3
0x13354  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x13359  ldarg.1
0x1335a  ldnull
0x1335b  ceq
0x1335d  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CheckCanSetCaseOnHold(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext, bool isCreate)
0x13362  ldc.i4.0
0x13363  ret
0x13364  ldarg.3
0x13365  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x1336a  ldarg.s  4
0x1336c  ldarg.2
0x1336d  ldnull
0x1336e  ceq
0x13370  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::UpdateCase(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext, valuetype [mscorlib]System.Guid entityId, bool isCreate)
0x13375  ret
0x13376  ldarg.s  5
0x13378  brfalse.s loc_133F4
0x1337a  ldarg.s  5
0x1337c  ldstr    aLastonholdtime// "lastonholdtime"
0x13381  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x13386  brfalse.s loc_133F4
0x13388  newobj   instance void Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::.ctor()
0x1338d  stloc.s  6
0x1338f  ldarg.s  5
0x13391  ldstr    aLastonholdtime// "lastonholdtime"
0x13396  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1339b  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x133a0  stloc.s  7
0x133a2  ldloc.s  7
0x133a4  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x133a9  ldc.i4.1
0x133aa  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x133af  ldc.i4.1
0x133b0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x133b5  stloc.s  7
0x133b7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x133bc  stloc.s  8
0x133be  ldloc.1
0x133bf  conv.r8
0x133c0  ldloc.s  6
0x133c2  ldloc.s  7
0x133c4  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x133c9  ldloc.s  8
0x133cb  ldarg.s  6
0x133cd  ldarg.3
0x133ce  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x133d3  callvirt instance float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateMinutesSpent(valuetype [mscorlib]System.DateTime startTime, valuetype [mscorlib]System.DateTime endTime, valuetype [mscorlib]System.Guid calendarId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x133d8  add
0x133d9  conv.i4
0x133da  stloc.1
0x133db  ldarg.3
0x133dc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x133e1  ldarg.s  4
0x133e3  ldloc.1
0x133e4  conv.r8
0x133e5  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::UpdateCaseOnHoldTime(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid incidentId, float64 caseOnHoldTime)
0x133ea  ldarg.s  8
0x133ec  ldloc.1
0x133ed  stind.i4
0x133ee  ldarg.s  7
0x133f0  ldc.i4.0
0x133f1  stind.i4
0x133f2  ldc.i4.1
0x133f3  ret
0x133f4  ldarg.s  7
0x133f6  ldc.i4.0
0x133f7  stind.i4
0x133f8  ldarg.s  8
0x133fa  ldloc.1
0x133fb  stind.i4
0x133fc  ldc.i4.0
0x133fd  ret
```
