# Microsoft.Crm.ObjectModel.WorkflowPluginHelper::TryGetValidBpfInfo

- ea: `0x137c20`
- end: `0x137e5f`
- name: `Microsoft.Crm.ObjectModel.WorkflowPluginHelper::TryGetValidBpfInfo`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x136320`

## callees

- `0x136ce0`
- `0x136cf0`
- `0x136d00`
- `0x136d10`
- `0x136d30`
- `0x136d80`
- `0x137c20`
- `0x1381a0`
- `0x138450`
- `0x1d0230`

## string_xrefs

- `0x137d3b`: `processid`
- `0x137d55`: `processid`
- `0x137d72`: `processid`
- `0x137dd8`: `processid`
- `0x137de6`: `processid`
- `0x137c61`: `traversedpath`
- `0x137c73`: `traversedpath`
- `0x137c8c`: `traversedpath`
- `0x137ca2`: `'traversedpath' attribute value is invalid.`

## pseudocode

```c

```

## disassembly

```asm
0x137c20  ldarg.0
0x137c21  castclass [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPipelineExecutionContext
0x137c26  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPipelineExecutionContext::get_PlatformContext()
0x137c2b  stloc.0
0x137c2c  ldarg.2
0x137c2d  newobj   instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::.ctor()
0x137c32  stind.ref
0x137c33  ldarg.2
0x137c34  ldind.ref
0x137c35  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x137c3a  callvirt instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::set_ActiveStageId(valuetype [mscorlib]System.Guid value)
0x137c3f  ldarg.2
0x137c40  ldind.ref
0x137c41  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x137c46  callvirt instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::set_ProcessId(valuetype [mscorlib]System.Guid value)
0x137c4b  ldarg.2
0x137c4c  ldind.ref
0x137c4d  ldsfld   string [mscorlib]System.String::Empty
0x137c52  callvirt instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::set_TraversedPath(string value)
0x137c57  ldc.i4.0
0x137c58  stloc.1
0x137c59  ldc.i4.0
0x137c5a  stloc.2
0x137c5b  ldarg.1
0x137c5c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x137c61  ldstr    aTraversedpath// "traversedpath"
0x137c66  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x137c6b  brfalse.s loc_137C7F
0x137c6d  ldarg.1
0x137c6e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x137c73  ldstr    aTraversedpath// "traversedpath"
0x137c78  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x137c7d  brtrue.s loc_137C86
0x137c7f  ldsfld   string [mscorlib]System.String::Empty
0x137c84  br.s     loc_137C9B
0x137c86  ldarg.1
0x137c87  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x137c8c  ldstr    aTraversedpath// "traversedpath"
0x137c91  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x137c96  castclass [mscorlib]System.String
0x137c9b  call     bool Microsoft.Crm.ObjectModel.WorkflowPluginHelper::ValidateTraversedPathFormat(string path)
0x137ca0  brtrue.s loc_137CAD
0x137ca2  ldstr    aTraversedpathA// "'traversedpath' attribute value is inva"...
0x137ca7  newobj   instance void Microsoft.Crm.ObjectModel.CrmStringAttributeValidationException::.ctor(string message)
0x137cac  throw
0x137cad  ldarg.1
0x137cae  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x137cb3  ldstr    aStageid// "stageid"
0x137cb8  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x137cbd  brfalse.s loc_137D35
0x137cbf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x137cc4  stloc.3
0x137cc5  ldloca.s 3
0x137cc7  ldarg.1
0x137cc8  ldstr    aStageid// "stageid"
0x137ccd  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x137cd2  constrained. [mscorlib]System.Guid
0x137cd8  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x137cdd  brtrue.s loc_137D35
0x137cdf  ldarg.1
0x137ce0  ldstr    aStageid// "stageid"
0x137ce5  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x137cea  brfalse.s loc_137D35
0x137cec  ldarg.1
0x137ced  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x137cf2  ldstr    aStageid// "stageid"
0x137cf7  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x137cfc  stloc.s  4
0x137cfe  ldloc.s  4
0x137d00  isinst   [mscorlib]System.Guid
0x137d05  brfalse.s loc_137D17
0x137d07  ldarg.2
0x137d08  ldind.ref
0x137d09  ldloc.s  4
0x137d0b  unbox.any [mscorlib]System.Guid
0x137d10  callvirt instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::set_ActiveStageId(valuetype [mscorlib]System.Guid value)
0x137d15  br.s     loc_137D33
0x137d17  ldloc.s  4
0x137d19  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x137d1e  brfalse.s loc_137D33
0x137d20  ldarg.2
0x137d21  ldind.ref
0x137d22  ldloc.s  4
0x137d24  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x137d29  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x137d2e  callvirt instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::set_ActiveStageId(valuetype [mscorlib]System.Guid value)
0x137d33  ldc.i4.1
0x137d34  stloc.1
0x137d35  ldarg.1
0x137d36  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x137d3b  ldstr    aProcessid// "processid"
0x137d40  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x137d45  brfalse.s loc_137DB7
0x137d47  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x137d4c  stloc.3
0x137d4d  ldloca.s 3
0x137d4f  ldarg.1
0x137d50  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x137d55  ldstr    aProcessid// "processid"
0x137d5a  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x137d5f  constrained. [mscorlib]System.Guid
0x137d65  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x137d6a  brtrue.s loc_137DB7
0x137d6c  ldarg.1
0x137d6d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x137d72  ldstr    aProcessid// "processid"
0x137d77  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x137d7c  stloc.s  5
0x137d7e  ldloc.s  5
0x137d80  isinst   [mscorlib]System.Guid
0x137d85  brfalse.s loc_137D97
0x137d87  ldarg.2
0x137d88  ldind.ref
0x137d89  ldloc.s  5
0x137d8b  unbox.any [mscorlib]System.Guid
0x137d90  callvirt instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::set_ProcessId(valuetype [mscorlib]System.Guid value)
0x137d95  br.s     loc_137DB3
0x137d97  ldloc.s  5
0x137d99  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x137d9e  brfalse.s loc_137DB3
0x137da0  ldarg.2
0x137da1  ldind.ref
0x137da2  ldloc.s  5
0x137da4  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x137da9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x137dae  callvirt instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::set_ProcessId(valuetype [mscorlib]System.Guid value)
0x137db3  ldc.i4.1
0x137db4  stloc.2
0x137db5  br.s     loc_137E2B
0x137db7  ldarg.0
0x137db8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PreEntityImages()
0x137dbd  ldstr    aPrebusinessent// "PreBusinessEntity"
0x137dc2  ldloca.s 6
0x137dc4  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::TryGetValue(var<u1>, !!T0)
0x137dc9  stloc.s  7
0x137dcb  ldloc.1
0x137dcc  ldloc.s  7
0x137dce  and
0x137dcf  brfalse.s loc_137E2B
0x137dd1  ldloc.s  6
0x137dd3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x137dd8  ldstr    aProcessid// "processid"
0x137ddd  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x137de2  brfalse.s loc_137E2B
0x137de4  ldloc.s  6
0x137de6  ldstr    aProcessid// "processid"
0x137deb  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x137df0  stloc.s  8
0x137df2  ldloc.s  8
0x137df4  isinst   [mscorlib]System.Guid
0x137df9  brfalse.s loc_137E0D
0x137dfb  ldarg.2
0x137dfc  ldind.ref
0x137dfd  ldloc.s  8
0x137dff  unbox.any [mscorlib]System.Guid
0x137e04  callvirt instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::set_ProcessId(valuetype [mscorlib]System.Guid value)
0x137e09  ldc.i4.1
0x137e0a  stloc.2
0x137e0b  br.s     loc_137E2B
0x137e0d  ldloc.s  8
0x137e0f  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x137e14  brfalse.s loc_137E2B
0x137e16  ldarg.2
0x137e17  ldind.ref
0x137e18  ldloc.s  8
0x137e1a  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x137e1f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x137e24  callvirt instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::set_ProcessId(valuetype [mscorlib]System.Guid value)
0x137e29  ldc.i4.1
0x137e2a  stloc.2
0x137e2b  ldloc.1
0x137e2c  ldloc.2
0x137e2d  and
0x137e2e  brfalse.s loc_137E5B
0x137e30  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.BusinessProcessFlowAbstractFactory::get_Instance()
0x137e35  ldloc.0
0x137e36  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateExecutionContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x137e3b  stloc.s  9
0x137e3d  ldarg.2
0x137e3e  ldind.ref
0x137e3f  ldarg.0
0x137e40  ldloc.s  9
0x137e42  ldarg.1
0x137e43  ldarg.2
0x137e44  ldind.ref
0x137e45  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_ActiveStageId()
0x137e4a  ldarg.2
0x137e4b  ldind.ref
0x137e4c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.BPFInstanceAttributes::get_ProcessId()
0x137e51  call     string Microsoft.Crm.ObjectModel.WorkflowPluginHelper::GetCandidateTraversedPath(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IExecutionContext executionContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, valuetype [mscorlib]System.Guid activeStageId, valuetype [mscorlib]System.Guid processId)
0x137e56  callvirt instance void Microsoft.Crm.ObjectModel.BPFInstanceAttributes::set_TraversedPath(string value)
0x137e5b  ldloc.1
0x137e5c  ldloc.2
0x137e5d  and
0x137e5e  ret
```
