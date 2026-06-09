# Microsoft.Crm.Workflow.Services.ProxyCustomActivity::Execute

- ea: `0x15240`
- end: `0x1558f`
- name: `Microsoft.Crm.Workflow.Services.ProxyCustomActivity::Execute`
- size: `847`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x10`
- `0x6890`
- `0x150b0`
- `0x15200`
- `0x15220`
- `0x15240`
- `0x1d3e0`
- `0x2e760`

## string_xrefs

- `0x153e7`: `PluginTrace`
- `0x1541b`: `PluginTrace`
- `0x15427`: `Plugin/$`
- `0x1556e`: `Plugin/$`

## pseudocode

```c

```

## disassembly

```asm
0x15240  newobj   instance void <>c__DisplayClass13_0::.ctor()
0x15245  stloc.0
0x15246  call     bool Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::IsSandboxCustomActivityFeatureEnabled()
0x1524b  brtrue.s loc_1525D
0x1524d  ldstr    aCustomWorkflow// "Custom Workflow Activities are not supp"...
0x15252  ldc.i4   0x80045051
0x15257  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1525c  throw
0x1525d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x15262  stloc.1
0x15263  ldarg.0
0x15264  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Services.ProxyCustomActivity::get_ArgumentsFromReference()
0x15269  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::GetEnumerator()
0x1526e  stloc.2
0x1526f  br.s     loc_15297
0x15271  ldloca.s 2
0x15273  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::get_Current()
0x15278  stloc.3
0x15279  ldarg.1
0x1527a  ldloca.s 3
0x1527c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x15281  callvirt instance object [System.Activities]System.Activities.ActivityContext::GetValue(class [System.Activities]System.Activities.Argument)
0x15286  stloc.s  4
0x15288  ldloc.1
0x15289  ldloca.s 3
0x1528b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x15290  ldloc.s  4
0x15292  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x15297  ldloca.s 2
0x15299  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::MoveNext()
0x1529e  brtrue.s loc_15271
0x152a0  leave.s  loc_152B0
0x152a2  ldloca.s 2
0x152a4  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>
0x152aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x152af  endfinally
0x152b0  ldarg.0
0x152b1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData Microsoft.Crm.Workflow.Services.ProxyCustomActivity::_pluginAssemblyData
0x152b6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData::get_SourceType()
0x152bb  ldc.i4.3
0x152bc  bne.un.s loc_152D1
0x152be  ldc.i4   0x80050241
0x152c3  ldc.i4.s 0x41
0x152c5  ldc.i4.0
0x152c6  newarr   [mscorlib]System.Object
0x152cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, object[])
0x152d0  throw
0x152d1  ldloc.0
0x152d2  ldarg.1
0x152d3  callvirt T0x2B00000E
0x152d8  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass13_0::requestContext
0x152dd  ldloc.0
0x152de  ldloc.0
0x152df  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass13_0::requestContext
0x152e4  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext
0x152e9  stfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext <>c__DisplayClass13_0::customActivityExecutionContext
0x152ee  call     class [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Instance()
0x152f3  callvirt instance class [Autofac]Autofac.IContainer [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Container()
0x152f8  ldloc.0
0x152f9  ldftn    instance void <>c__DisplayClass13_0::<Execute>b__0(class [Autofac]Autofac.ContainerBuilder builder)
0x152ff  newobj   instance void class [mscorlib]System.Action`1<class [Autofac]Autofac.ContainerBuilder>::.ctor(object, native int)
0x15304  callvirt instance class [Autofac]Autofac.ILifetimeScope [Autofac]Autofac.ILifetimeScope::BeginLifetimeScope(class [mscorlib]System.Action`1<class [Autofac]Autofac.ContainerBuilder>)
0x15309  stloc.s  5
0x1530b  newobj   instance void [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::.ctor()
0x15310  dup
0x15311  ldarg.0
0x15312  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.ProxyCustomActivity::_pluginTypeId
0x15317  stfld    valuetype [mscorlib]System.Guid [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::pluginTypeId
0x1531c  dup
0x1531d  ldarg.0
0x1531e  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData Microsoft.Crm.Workflow.Services.ProxyCustomActivity::_pluginTypeData
0x15323  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::pluginTypeData
0x15328  dup
0x15329  ldarg.0
0x1532a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData Microsoft.Crm.Workflow.Services.ProxyCustomActivity::_pluginAssemblyData
0x1532f  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::pluginAssemblyData
0x15334  dup
0x15335  ldloc.0
0x15336  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext <>c__DisplayClass13_0::requestContext
0x1533b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x15340  stfld    valuetype [mscorlib]System.Guid [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::orgId
0x15345  dup
0x15346  ldsfld   string [mscorlib]System.String::Empty
0x1534b  stfld    string [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::stepDescriptionConfiguration
0x15350  dup
0x15351  ldsfld   string [mscorlib]System.String::Empty
0x15356  stfld    string [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::stepDescriptionSecureConfiguration
0x1535b  dup
0x1535c  ldc.i4.1
0x1535d  stfld    valuetype [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemoteCodeUnitType [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest::remoteCodeUnitType
0x15362  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactory::CreateRemotePlugin(class [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.RemotePluginFactoryRequest)
0x15367  stloc.s  6
0x15369  newobj   instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection::.ctor()
0x1536e  stloc.s  7
0x15370  ldloc.1
0x15371  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::GetEnumerator()
0x15376  stloc.s  8
0x15378  br.s     loc_15398
0x1537a  ldloca.s 8
0x1537c  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::get_Current()
0x15381  stloc.s  9
0x15383  ldloc.s  7
0x15385  ldloca.s 9
0x15387  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1538c  ldloca.s 9
0x1538e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x15393  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x15398  ldloca.s 8
0x1539a  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::MoveNext()
0x1539f  brtrue.s loc_1537A
0x153a1  leave.s  loc_153B1
0x153a3  ldloca.s 8
0x153a5  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>
0x153ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x153b0  endfinally
0x153b1  ldloc.0
0x153b2  ldfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext <>c__DisplayClass13_0::customActivityExecutionContext
0x153b7  ldloc.s  7
0x153b9  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::set_Arguments(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection)
0x153be  ldloc.s  6
0x153c0  ldloc.s  5
0x153c2  newobj   instance void Services.WorkflowServiceProvider::.ctor(class [Autofac]Autofac.ILifetimeScope lifecycleScope)
0x153c7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin::Execute(class [mscorlib]System.IServiceProvider)
0x153cc  leave    loc_15469
0x153d1  stloc.s  0xA
0x153d3  ldarg.1
0x153d4  callvirt T0x2B000009
0x153d9  callvirt instance class Microsoft.Crm.Workflow.WorkflowTracingService Microsoft.Crm.Workflow.ICommonWorkflowContext::get_WorkflowTracingService()
0x153de  stloc.s  0xB
0x153e0  ldloc.s  0xA
0x153e2  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x153e7  ldstr    aPlugintrace// "PluginTrace"
0x153ec  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x153f1  isinst   [mscorlib]System.String
0x153f6  stloc.s  0xC
0x153f8  ldloc.s  0xC
0x153fa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x153ff  brtrue.s loc_15425
0x15401  ldloc.s  0xB
0x15403  brfalse.s loc_15425
0x15405  ldloc.s  0xB
0x15407  ldloc.s  0xC
0x15409  ldc.i4.0
0x1540a  newarr   [mscorlib]System.Object
0x1540f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService::Trace(string, object[])
0x15414  ldloc.s  0xA
0x15416  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1541b  ldstr    aPlugintrace// "PluginTrace"
0x15420  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x15425  ldloc.s  0xA
0x15427  ldstr    aPlugin// "Plugin/$"
0x1542c  ldtoken  Microsoft.Crm.Workflow.Services.ProxyCustomActivity
0x15431  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15436  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1543b  call     string [mscorlib]System.String::Concat(string, string)
0x15440  call     void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.PipelineErrorHandling::AddExceptionSourceIfNotExists(class [mscorlib]System.Exception, string)
0x15445  ldloc.s  0xA
0x15447  ldarg.0
0x15448  ldfld    string Microsoft.Crm.Workflow.Services.ProxyCustomActivity::_assemblyQualifiedName
0x1544d  ldarg.0
0x1544e  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData Microsoft.Crm.Workflow.Services.ProxyCustomActivity::_pluginTypeData
0x15453  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_PluginTypeName()
0x15458  ldarg.0
0x15459  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData Microsoft.Crm.Workflow.Services.ProxyCustomActivity::_pluginAssemblyData
0x1545e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData::get_PluginAssemblyName()
0x15463  newobj   instance void Microsoft.Crm.Workflow.Services.InvalidCustomActivityExecutionException::.ctor(class [mscorlib]System.Exception exception, string customActivityAssemblyQualifiedName, string customActivityTypeName, string customActivityAssemblyName)
0x15468  throw
0x15469  leave.s  loc_15477
0x1546b  ldloc.s  5
0x1546d  brfalse.s loc_15476
0x1546f  ldloc.s  5
0x15471  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15476  endfinally
0x15477  ldloc.0
0x15478  ldfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext <>c__DisplayClass13_0::customActivityExecutionContext
0x1547d  brfalse  loc_1556C
0x15482  ldloc.0
0x15483  ldfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext <>c__DisplayClass13_0::customActivityExecutionContext
0x15488  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::get_Arguments()
0x1548d  brfalse  loc_1556C
0x15492  ldarg.0
0x15493  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Services.ProxyCustomActivity::get_ArgumentsFromReference()
0x15498  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::GetEnumerator()
0x1549d  stloc.2
0x1549e  br.s     loc_154E6
0x154a0  ldloca.s 2
0x154a2  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::get_Current()
0x154a7  stloc.s  0xD
0x154a9  ldloc.0
0x154aa  ldfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext <>c__DisplayClass13_0::customActivityExecutionContext
0x154af  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::get_Arguments()
0x154b4  ldloca.s 0xD
0x154b6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x154bb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x154c0  brfalse.s loc_154E6
0x154c2  ldarg.1
0x154c3  ldloca.s 0xD
0x154c5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x154ca  ldloc.0
0x154cb  ldfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext <>c__DisplayClass13_0::customActivityExecutionContext
0x154d0  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::get_Arguments()
0x154d5  ldloca.s 0xD
0x154d7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x154dc  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x154e1  callvirt instance void [System.Activities]System.Activities.ActivityContext::SetValue(class [System.Activities]System.Activities.Argument, object)
0x154e6  ldloca.s 2
0x154e8  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::MoveNext()
0x154ed  brtrue.s loc_154A0
0x154ef  leave.s  loc_154FF
0x154f1  ldloca.s 2
0x154f3  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>
0x154f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x154fe  endfinally
0x154ff  ldarg.0
0x15500  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Services.ProxyCustomActivity::get_OutArgumentsFromReference()
0x15505  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::GetEnumerator()
0x1550a  stloc.2
0x1550b  br.s     loc_15553
0x1550d  ldloca.s 2
0x1550f  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::get_Current()
0x15514  stloc.s  0xE
0x15516  ldloc.0
0x15517  ldfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext <>c__DisplayClass13_0::customActivityExecutionContext
0x1551c  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::get_Arguments()
0x15521  ldloca.s 0xE
0x15523  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x15528  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x1552d  brfalse.s loc_15553
0x1552f  ldarg.1
0x15530  ldloca.s 0xE
0x15532  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x15537  ldloc.0
0x15538  ldfld    class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext <>c__DisplayClass13_0::customActivityExecutionContext
0x1553d  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentsCollection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivityExecutionContext::get_Arguments()
0x15542  ldloca.s 0xE
0x15544  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x15549  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1554e  callvirt instance void [System.Activities]System.Activities.ActivityContext::SetValue(class [System.Activities]System.Activities.Argument, object)
0x15553  ldloca.s 2
0x15555  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::MoveNext()
0x1555a  brtrue.s loc_1550D
0x1555c  leave.s  loc_1556C
0x1555e  ldloca.s 2
0x15560  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>
0x15566  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1556b  endfinally
0x1556c  leave.s  loc_1558E
0x1556e  ldstr    aPlugin// "Plugin/$"
0x15573  ldtoken  Microsoft.Crm.Workflow.Services.ProxyCustomActivity
0x15578  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1557d  callvirt instance string [mscorlib]System.Type::get_FullName()
0x15582  call     string [mscorlib]System.String::Concat(string, string)
0x15587  call     void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.PipelineErrorHandling::AddExceptionSourceIfNotExists(class [mscorlib]System.Exception, string)
0x1558c  rethrow
0x1558e  ret
```
