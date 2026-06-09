# Microsoft.Crm.ObjectModel.GlobalActiveStagePlugin::Execute

- ea: `0x136320`
- end: `0x13661d`
- name: `Microsoft.Crm.ObjectModel.GlobalActiveStagePlugin::Execute`
- size: `765`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x136320`
- `0x136630`
- `0x136680`
- `0x136730`
- `0x136ce0`
- `0x136d00`
- `0x136d20`
- `0x136d60`
- `0x137800`
- `0x137840`
- `0x1378a0`
- `0x137c20`
- `0x137e60`
- `0x137f10`
- `0x137f70`
- `0x138220`

## string_xrefs

- `0x136321`: `serviceProvider`
- `0x136484`: `Create`
- `0x1364fe`: `Create`
- `0x136539`: `Update`
- `0x136458`: `Delete`
- `0x1363b1`: `processid`
- `0x1363c6`: `processid`
- `0x1363d8`: `processid`
- `0x1363ef`: `processid`
- `0x136411`: `processid`
- `0x13634e`: `pluginExecutionContext`
- `0x13643b`: `LegacyBPFCreateOrUpdate`
- `0x1365b1`: `GlobalActiveStagePlugin`
- `0x1365b6`: `GlobalActiveStagePlugin.Execute`
- `0x1365c6`: `GlobalActiveStage plugin is for SdkMessage = {0} and pipeline depth = {1}`
- `0x136600`: `Error occured while executing GlobalActiveStagePlugin. Error Message : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x136320  ldarg.1
0x136321  ldstr    aServiceprovide// "serviceProvider"
0x136326  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13632b  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x136330  stloc.0
0x136331  ldloc.0
0x136332  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x136337  ldarg.1
0x136338  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x13633d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x136342  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x136347  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x13634c  stloc.1
0x13634d  ldloc.1
0x13634e  ldstr    aPluginexecutio// "pluginExecutionContext"
0x136353  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x136358  ldloc.1
0x136359  ldloca.s 2
0x13635b  call     bool Microsoft.Crm.ObjectModel.WorkflowPluginHelper::TryGetValidTargetEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, [out] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity& entity)
0x136360  brtrue.s loc_136363
0x136362  ret
0x136363  ldloc.1
0x136364  isinst   [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPipelineExecutionContext
0x136369  stloc.3
0x13636a  ldloc.3
0x13636b  ldstr    aPipelinecontex// "pipelineContext"
0x136370  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x136375  ldarg.0
0x136376  ldloc.1
0x136377  call     instance bool Microsoft.Crm.ObjectModel.GlobalActiveStagePlugin::IsBusinessProcessEnabled(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context)
0x13637c  brtrue.s loc_13637F
0x13637e  ret
0x13637f  ldloc.3
0x136380  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPipelineExecutionContext::get_PlatformContext()
0x136385  ldstr    aPipelinecontex_0// "pipelineContext.PlatformContext"
0x13638a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13638f  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowAbstractFactory::get_Instance()
0x136394  dup
0x136395  ldloc.3
0x136396  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPipelineExecutionContext::get_PlatformContext()
0x13639b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateExecutionContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1363a0  stloc.s  4
0x1363a2  ldloc.s  4
0x1363a4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IProcessUnificationFeature [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateProcessUnificationFeature(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext)
0x1363a9  stloc.s  5
0x1363ab  ldloc.2
0x1363ac  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1363b1  ldstr    aProcessid// "processid"
0x1363b6  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x1363bb  brfalse  loc_13644B
0x1363c0  ldloc.2
0x1363c1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1363c6  ldstr    aProcessid// "processid"
0x1363cb  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1363d0  brfalse.s loc_13644B
0x1363d2  ldloc.2
0x1363d3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1363d8  ldstr    aProcessid// "processid"
0x1363dd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1363e2  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1363e7  beq.s    loc_13644B
0x1363e9  ldloc.2
0x1363ea  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1363ef  ldstr    aProcessid// "processid"
0x1363f4  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1363f9  unbox.any [mscorlib]System.Guid
0x1363fe  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x136403  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x136408  brfalse.s loc_13640B
0x13640a  ret
0x13640b  ldloc.2
0x13640c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x136411  ldstr    aProcessid// "processid"
0x136416  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x13641b  unbox.any [mscorlib]System.Guid
0x136420  ldloc.1
0x136421  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x136426  ldstr    asc_27B0C2// ":"
0x13642b  ldloc.2
0x13642c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x136431  box      [mscorlib]System.Guid
0x136436  call     string [mscorlib]System.String::Concat(object, object, object)
0x13643b  ldstr    aLegacybpfcreat// "LegacyBPFCreateOrUpdate"
0x136440  ldloc.3
0x136441  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPipelineExecutionContext::get_PlatformContext()
0x136446  call     void Microsoft.Crm.ObjectModel.WorkflowPluginHelper::LogTelemetryEventForBpf(valuetype [mscorlib]System.Guid processId, string operationName, string subFeatureName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x13644b  newobj   instance void Microsoft.Crm.ObjectModel.WorkflowPluginHelper::.ctor()
0x136450  stloc.s  6
0x136452  ldloc.1
0x136453  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x136458  ldstr    aDelete// "Delete"
0x13645d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x136462  brfalse.s loc_136473
0x136464  ldloc.s  6
0x136466  ldloc.2
0x136467  ldloc.s  4
0x136469  callvirt instance void Microsoft.Crm.ObjectModel.WorkflowPluginHelper::HandlingParticipatingEntityDelete(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext context)
0x13646e  br       loc_136573
0x136473  ldloc.1
0x136474  ldloc.2
0x136475  ldloca.s 7
0x136477  call     bool Microsoft.Crm.ObjectModel.WorkflowPluginHelper::TryGetValidBpfInfo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [out] class Microsoft.Crm.ObjectModel.BPFInstanceAttributes& bpfAttributes)
0x13647c  brtrue.s loc_1364BE
0x13647e  ldloc.1
0x13647f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x136484  ldstr    aCreate// "Create"
0x136489  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x13648e  brfalse.s loc_136495
0x136490  leave    loc_13661C
0x136495  ldloc.2
0x136496  ldloc.1
0x136497  ldloc.s  7
0x136499  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_ProcessId()
0x13649e  ldloca.s 7
0x1364a0  call     bool Microsoft.Crm.ObjectModel.GlobalActiveStagePlugin::TryGetDefaultProcessInfo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, valuetype [mscorlib]System.Guid processId, [out] class Microsoft.Crm.ObjectModel.BPFInstanceAttributes& bpfAttributes)
0x1364a5  brtrue.s loc_1364AC
0x1364a7  leave    loc_13661C
0x1364ac  ldloc.s  5
0x1364ae  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IProcessUnificationFeature::get_FeatureEnabledV2()
0x1364b3  brtrue.s loc_1364BE
0x1364b5  ldloc.2
0x1364b6  ldloc.1
0x1364b7  ldloc.s  7
0x1364b9  call     void Microsoft.Crm.ObjectModel.GlobalActiveStagePlugin::UpdateEntityProcessInfo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, class Microsoft.Crm.ObjectModel.BPFInstanceAttributes bpfAttributes)
0x1364be  ldloc.2
0x1364bf  ldloc.1
0x1364c0  ldloc.s  4
0x1364c2  ldloc.s  7
0x1364c4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_ProcessId()
0x1364c9  ldloca.s 8
0x1364cb  call     bool Microsoft.Crm.ObjectModel.WorkflowPluginHelper::TryGetValidWorkflowOm(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext executionContext, valuetype [mscorlib]System.Guid processId, [out] class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep& workflowStep)
0x1364d0  brtrue.s loc_1364D7
0x1364d2  leave    loc_13661C
0x1364d7  ldloc.2
0x1364d8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x1364dd  ldloc.s  8
0x1364df  call     valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetEntityPosition(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1364e4  stloc.s  9
0x1364e6  ldloc.s  9
0x1364e8  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetAttributeNameForEntityId(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition)
0x1364ed  stloc.s  0xA
0x1364ef  ldloc.s  9
0x1364f1  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetAttributeNameForEntityOtc(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition)
0x1364f6  stloc.s  0xB
0x1364f8  ldloc.1
0x1364f9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x1364fe  ldstr    aCreate// "Create"
0x136503  call     bool [mscorlib]System.String::op_Equality(string, string)
0x136508  brfalse.s loc_136533
0x13650a  ldloc.2
0x13650b  ldloc.s  7
0x13650d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_ProcessId()
0x136512  ldloc.s  9
0x136514  ldloc.s  7
0x136516  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_ActiveStageId()
0x13651b  ldloc.s  7
0x13651d  callvirt instance string Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_TraversedPath()
0x136522  ldloc.s  7
0x136524  callvirt instance string Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_Name()
0x136529  ldloc.s  4
0x13652b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.WorkflowPluginHelper::CreateBpfEntityInstance(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, valuetype [mscorlib]System.Guid processId, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition entityPosition, valuetype [mscorlib]System.Guid activeStageId, string traversedPath, string name, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext context)
0x136530  pop
0x136531  br.s     loc_136573
0x136533  ldloc.1
0x136534  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x136539  ldstr    aUpdate// "Update"
0x13653e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x136543  brfalse.s loc_136573
0x136545  ldloc.s  6
0x136547  ldloc.s  7
0x136549  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_ActiveStageId()
0x13654e  ldloc.s  7
0x136550  callvirt instance string Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_TraversedPath()
0x136555  ldloc.s  0xB
0x136557  ldloc.s  0xA
0x136559  ldloc.s  9
0x13655b  ldloc.s  7
0x13655d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_ProcessId()
0x136562  ldloc.s  7
0x136564  callvirt instance string Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_Name()
0x136569  ldloc.2
0x13656a  ldloc.1
0x13656b  ldloc.s  4
0x13656d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.WorkflowPluginHelper::CreateOrUpdateBpfInstance(valuetype [mscorlib]System.Guid activeStageId, string traversedPath, string attributeOtcName, string attributeIdName, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.EntityPosition entityPosition, valuetype [mscorlib]System.Guid processId, string name, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext executionContext)
0x136572  pop
0x136573  ldloc.0
0x136574  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x136579  call     class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.WorkflowTelemetryEventSource [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.WorkflowTelemetryEventSource::get_Instance()
0x13657e  ldloc.1
0x13657f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x136584  ldloc.1
0x136585  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x13658a  stloc.s  0xC
0x13658c  ldloca.s 0xC
0x13658e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x136593  brtrue.s loc_13659C
0x136595  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13659a  br.s     loc_1365AB
0x13659c  ldloc.1
0x13659d  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x1365a2  stloc.s  0xC
0x1365a4  ldloca.s 0xC
0x1365a6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1365ab  ldloc.1
0x1365ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x1365b1  ldstr    aGlobalactivest// "GlobalActiveStagePlugin"
0x1365b6  ldstr    aGlobalactivest_0// "GlobalActiveStagePlugin.Execute"
0x1365bb  ldloc.0
0x1365bc  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x1365c1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1365c6  ldstr    aGlobalactivest_1// "GlobalActiveStage plugin is for SdkMess"...
0x1365cb  ldc.i4.2
0x1365cc  newarr   [mscorlib]System.Object
0x1365d1  dup
0x1365d2  ldc.i4.0
0x1365d3  ldloc.1
0x1365d4  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x1365d9  stelem.ref
0x1365da  dup
0x1365db  ldc.i4.1
0x1365dc  ldloc.1
0x1365dd  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x1365e2  box      [mscorlib]System.Int32
0x1365e7  stelem.ref
0x1365e8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1365ed  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ObjectModel.WorkflowTelemetryEventSource::LogProcessUnificationPerfExecutionTime(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, string, int64, string)
0x1365f2  leave.s  loc_13661C
0x1365f4  stloc.s  0xD
0x1365f6  ldloc.s  0xD
0x1365f8  ldloc.1
0x1365f9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x1365fe  ldc.i4.s 0x11
0x136600  ldstr    aErrorOccuredWh_1// "Error occured while executing GlobalAct"...
0x136605  ldc.i4.1
0x136606  newarr   [mscorlib]System.Object
0x13660b  dup
0x13660c  ldc.i4.0
0x13660d  ldloc.s  0xD
0x13660f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x136614  stelem.ref
0x136615  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13661a  rethrow
0x13661c  ret
```
