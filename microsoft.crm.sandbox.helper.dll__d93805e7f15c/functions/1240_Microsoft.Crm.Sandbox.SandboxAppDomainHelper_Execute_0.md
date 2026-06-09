# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::Execute_0

- ea: `0x1240`
- end: `0x16e1`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::Execute_0`
- size: `1185`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x720`
- `0xe60`
- `0x1010`
- `0x1060`
- `0x10d0`
- `0x1240`
- `0x1790`
- `0x18d0`
- `0x1990`
- `0x1a20`
- `0x1ba0`
- `0x1c00`
- `0x1e80`
- `0x21d0`
- `0x21f0`

## string_xrefs

- `0x12c3`: `SandboxAppDomainHelper.Execute.CreateSandboxCodeUnit`
- `0x12fa`: `SandboxAppDomainHelper.Execute: exception from plugin constructor: `
- `0x1452`: `PluginExecutionTimeout`
- `0x1464`: `PluginExecutionTimeout`
- `0x1645`: `ExceptionFromPluginConstructor`
- `0x167c`: `ExceptionFromPluginConstructor`
- `0x1656`: `ExceptionFromPluginExecute`
- `0x1692`: `ExceptionFromPluginExecute`
- `0x14f8`: `Couldn’t complete execution of the custom activity `

## pseudocode

```c

```

## disassembly

```asm
0x1240  ldarg.3
0x1241  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x1246  stloc.0
0x1247  ldc.i4.1
0x1248  stloc.1
0x1249  ldstr    aSandboxappdoma_11// "SandboxAppDomainHelper.Execute"
0x124e  ldc.i4.3
0x124f  ldloc.0
0x1250  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x1255  stloc.2
0x1256  ldarg.s  6
0x1258  call     void Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ChaosFailure(bool chaosFailAppDomain)
0x125d  ldstr    aSandboxappdoma_12// "SandboxAppDomainHelper.Execute.Validate"...
0x1262  ldc.i4.3
0x1263  ldloc.0
0x1264  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x1269  stloc.s  6
0x126b  ldarg.0
0x126c  ldarg.2
0x126d  ldarg.3
0x126e  ldarg.s  4
0x1270  call     instance void Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ValidateArguments(string typeName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext requestContext, class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> sandboxServices)
0x1275  leave.s  loc_1283
0x1277  ldloc.s  6
0x1279  brfalse.s loc_1282
0x127b  ldloc.s  6
0x127d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1282  endfinally
0x1283  ldloc.0
0x1284  ldc.i4.3
0x1285  ldstr    aSandboxappdoma_13// "SandboxAppDomainHelper.Execute: enter"
0x128a  ldnull
0x128b  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1290  ldarg.0
0x1291  ldarg.1
0x1292  call     instance void Microsoft.Crm.Sandbox.SandboxAppDomainHelper::SetProxyTypesAssembly(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory)
0x1297  ldarg.s  4
0x1299  newobj   instance void Microsoft.Crm.Sandbox.SandboxServiceProvider::.ctor(class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> services)
0x129e  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService
0x12a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12a8  callvirt instance object Microsoft.Crm.Sandbox.SandboxServiceProvider::GetService(class [mscorlib]System.Type serviceType)
0x12ad  castclass Microsoft.Crm.Sandbox.SandboxTracingService
0x12b2  stloc.3
0x12b3  ldc.i4.0
0x12b4  stloc.s  4
0x12b6  ldc.i4.0
0x12b7  stloc.s  5
0x12b9  newobj   instance void <>c__DisplayClass21_0::.ctor()
0x12be  stloc.s  7
0x12c0  ldnull
0x12c1  stloc.s  8
0x12c3  ldstr    aSandboxappdoma_19// "SandboxAppDomainHelper.Execute.CreateSa"...
0x12c8  ldc.i4.3
0x12c9  ldloc.0
0x12ca  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x12cf  stloc.s  6
0x12d1  ldc.i4.0
0x12d2  stloc.1
0x12d3  ldarg.0
0x12d4  ldnull
0x12d5  ldnull
0x12d6  ldarg.2
0x12d7  call     instance object Microsoft.Crm.Sandbox.SandboxAppDomainHelper::CreateSandboxCodeUnit(class [mscorlib]System.Reflection.ConstructorInfo constructorInfo, object[] args, string typeName)
0x12dc  stloc.s  8
0x12de  leave.s  loc_12EC
0x12e0  ldloc.s  6
0x12e2  brfalse.s loc_12EB
0x12e4  ldloc.s  6
0x12e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12eb  endfinally
0x12ec  leave.s  loc_132C
0x12ee  stloc.s  0xC
0x12f0  ldloc.0
0x12f1  ldc.i4.1
0x12f2  ldc.i4.4
0x12f3  newarr   [mscorlib]System.Object
0x12f8  dup
0x12f9  ldc.i4.0
0x12fa  ldstr    aSandboxappdoma_20// "SandboxAppDomainHelper.Execute: excepti"...
0x12ff  stelem.ref
0x1300  dup
0x1301  ldc.i4.1
0x1302  ldloc.s  0xC
0x1304  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1309  stelem.ref
0x130a  dup
0x130b  ldc.i4.2
0x130c  ldstr    asc_38FC// ": "
0x1311  stelem.ref
0x1312  dup
0x1313  ldc.i4.3
0x1314  ldloc.s  0xC
0x1316  callvirt instance string [mscorlib]System.Object::ToString()
0x131b  stelem.ref
0x131c  call     string [mscorlib]System.String::Concat(object[])
0x1321  ldnull
0x1322  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1327  ldc.i4.1
0x1328  stloc.s  4
0x132a  rethrow
0x132c  ldloc.s  7
0x132e  ldloc.s  8
0x1330  castclass [System.Activities]System.Activities.Activity
0x1335  newobj   instance void [System.Activities]System.Activities.WorkflowInvoker::.ctor(class [System.Activities]System.Activities.Activity)
0x133a  stfld    class [System.Activities]System.Activities.WorkflowInvoker <>c__DisplayClass21_0::wfInvoker
0x133f  ldarg.3
0x1340  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext
0x1345  stloc.s  9
0x1347  ldarg.3
0x1348  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWorkflowContext
0x134d  stloc.s  0xA
0x134f  ldloc.s  7
0x1351  ldfld    class [System.Activities]System.Activities.WorkflowInvoker <>c__DisplayClass21_0::wfInvoker
0x1356  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x135b  ldloc.s  9
0x135d  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1362  ldloc.s  7
0x1364  ldfld    class [System.Activities]System.Activities.WorkflowInvoker <>c__DisplayClass21_0::wfInvoker
0x1369  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x136e  ldloc.s  0xA
0x1370  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1375  ldloc.s  7
0x1377  ldfld    class [System.Activities]System.Activities.WorkflowInvoker <>c__DisplayClass21_0::wfInvoker
0x137c  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x1381  ldloc.3
0x1382  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x1387  ldarg.s  4
0x1389  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::GetEnumerator()
0x138e  stloc.s  0xD
0x1390  br.s     loc_13B3
0x1392  ldloca.s 0xD
0x1394  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [mscorlib]System.Type, object>::get_Current()
0x1399  stloc.s  0xE
0x139b  ldloc.s  7
0x139d  ldfld    class [System.Activities]System.Activities.WorkflowInvoker <>c__DisplayClass21_0::wfInvoker
0x13a2  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowInvoker::get_Extensions()
0x13a7  ldloca.s 0xE
0x13a9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, object>::get_Value()
0x13ae  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x13b3  ldloca.s 0xD
0x13b5  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [mscorlib]System.Type, object>::MoveNext()
0x13ba  brtrue.s loc_1392
0x13bc  leave.s  loc_13CC
0x13be  ldloca.s 0xD
0x13c0  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [mscorlib]System.Type, object>
0x13c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13cb  endfinally
0x13cc  ldstr    aSandboxappdoma_37// "SandboxAppDomainHelper.Execute.InvokeWi"...
0x13d1  ldc.i4.3
0x13d2  ldloc.0
0x13d3  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x13d8  stloc.s  6
0x13da  newobj   instance void <>c__DisplayClass21_1::.ctor()
0x13df  stloc.s  0xF
0x13e1  ldloc.s  0xF
0x13e3  ldloc.s  7
0x13e5  stfld    class <>c__DisplayClass21_0 <>c__DisplayClass21_1::CS$<>8__locals1
0x13ea  ldloc.s  0xF
0x13ec  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x13f1  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <>c__DisplayClass21_1::wfArguments
0x13f6  ldloc.s  9
0x13f8  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::get_Arguments()
0x13fd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::GetEnumerator()
0x1402  stloc.s  0x12
0x1404  br.s     loc_1429
0x1406  ldloc.s  0x12
0x1408  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x140d  stloc.s  0x13
0x140f  ldloc.s  0xF
0x1411  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <>c__DisplayClass21_1::wfArguments
0x1416  ldloca.s 0x13
0x1418  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x141d  ldloca.s 0x13
0x141f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x1424  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1429  ldloc.s  0x12
0x142b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1430  brtrue.s loc_1406
0x1432  leave.s  loc_1440
0x1434  ldloc.s  0x12
0x1436  brfalse.s loc_143F
0x1438  ldloc.s  0x12
0x143a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x143f  endfinally
0x1440  ldc.i4.s 0x78
0x1442  stloc.s  0x10
0x1444  ldarg.3
0x1445  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x144a  brfalse.s loc_1475
0x144c  ldarg.3
0x144d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x1452  ldstr    aPluginexecutio// "PluginExecutionTimeout"
0x1457  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x145c  brfalse.s loc_1475
0x145e  ldarg.3
0x145f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x1464  ldstr    aPluginexecutio// "PluginExecutionTimeout"
0x1469  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x146e  unbox.any [mscorlib]System.Int32
0x1473  stloc.s  0x10
0x1475  ldstr    aSandboxappdoma_38// "SandboxAppDomainHelper.Execute.Invoke"
0x147a  ldc.i4.3
0x147b  ldloc.0
0x147c  newobj   instance void Microsoft.Crm.Sandbox.SandboxPerformanceContextHelper::.ctor(string contextName, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [mscorlib]System.Guid orgId)
0x1481  stloc.s  0x14
0x1483  ldc.i4.0
0x1484  stloc.s  0x15
0x1486  ldarg.s  5
0x1488  brfalse.s loc_14B7
0x148a  ldarg.0
0x148b  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x1490  callvirt instance bool [mscorlib]System.Reflection.Assembly::get_IsFullyTrusted()
0x1495  brfalse.s loc_14B7
0x1497  ldarg.0
0x1498  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_organizationId
0x149d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14a2  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x14a7  brfalse.s loc_14B7
0x14a9  ldc.i4.1
0x14aa  stloc.s  0x15
0x14ac  ldc.i4.1
0x14ad  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x14b2  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x14b7  nop
0x14b8  call     class [mscorlib]System.Threading.Tasks.TaskFactory [mscorlib]System.Threading.Tasks.Task::get_Factory()
0x14bd  ldloc.s  0xF
0x14bf  ldftn    instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> <>c__DisplayClass21_1::<Execute>b__0()
0x14c5  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>>::.ctor(object, native int)
0x14ca  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x14cf  ldc.i4.8
0x14d0  call     class [mscorlib]System.Threading.Tasks.TaskScheduler [mscorlib]System.Threading.Tasks.TaskScheduler::get_Default()
0x14d5  callvirt T0x2B000002
0x14da  stloc.s  0x16
0x14dc  ldloc.s  0x16
0x14de  ldloc.s  0x10
0x14e0  conv.r8
0x14e1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x14e6  callvirt instance bool [mscorlib]System.Threading.Tasks.Task::Wait(valuetype [mscorlib]System.TimeSpan)
0x14eb  brfalse.s loc_14F8
0x14ed  ldloc.s  0x16
0x14ef  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>>::get_Result()
0x14f4  stloc.s  0x11
0x14f6  br.s     loc_150E
0x14f8  ldstr    aCouldnTComplet_0// "Couldn’t complete execution of the cust"...
0x14fd  ldarg.2
0x14fe  ldstr    aPlugInWithinTh// " plug-in within the 2-minute time limit"...
0x1503  call     string [mscorlib]System.String::Concat(string, string, string)
0x1508  newobj   instance void [mscorlib]System.TimeoutException::.ctor(string)
0x150d  throw
0x150e  leave.s  loc_1543
0x1510  stloc.s  0x17
0x1512  ldloc.s  0x17
0x1514  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception> [mscorlib]System.AggregateException::get_InnerExceptions()
0x1519  brfalse.s loc_1541
0x151b  ldloc.s  0x17
0x151d  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception> [mscorlib]System.AggregateException::get_InnerExceptions()
0x1522  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception>::get_Count()
0x1527  ldc.i4.1
0x1528  bne.un.s loc_1541
0x152a  ldloc.s  0x17
0x152c  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception> [mscorlib]System.AggregateException::get_InnerExceptions()
0x1531  ldc.i4.0
0x1532  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception>::get_Item(!!T0)
0x1537  call     class [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo::Capture(class [mscorlib]System.Exception)
0x153c  callvirt instance void [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo::Throw()
0x1541  rethrow
0x1543  leave.s  loc_154F
0x1545  ldloc.s  0x15
0x1547  brfalse.s loc_154E
0x1549  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x154e  endfinally
0x154f  leave.s  loc_155D
0x1551  ldloc.s  0x14
0x1553  brfalse.s loc_155C
0x1555  ldloc.s  0x14
0x1557  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x155c  endfinally
0x155d  ldloc.s  0x11
0x155f  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Keys()
0x1564  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x1569  stloc.s  0x18
0x156b  br.s     loc_15B6
0x156d  ldloc.s  0x18
0x156f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1574  stloc.s  0x19
0x1576  ldloc.s  9
0x1578  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::get_Arguments()
0x157d  ldloc.s  0x19
0x157f  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x1584  brfalse.s loc_159F
0x1586  ldloc.s  9
0x1588  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::get_Arguments()
0x158d  ldloc.s  0x19
0x158f  ldloc.s  0x11
0x1591  ldloc.s  0x19
0x1593  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x1598  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x159d  br.s     loc_15B6
0x159f  ldloc.s  9
0x15a1  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::get_Arguments()
  ... truncated ...
```
