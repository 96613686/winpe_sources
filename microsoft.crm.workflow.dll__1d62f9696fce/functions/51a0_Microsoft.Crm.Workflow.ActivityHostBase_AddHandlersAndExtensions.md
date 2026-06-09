# Microsoft.Crm.Workflow.ActivityHostBase::AddHandlersAndExtensions

- ea: `0x51a0`
- end: `0x54b6`
- name: `Microsoft.Crm.Workflow.ActivityHostBase::AddHandlersAndExtensions`
- size: `790`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10c20`
- `0x10f40`

## callees

- `0x51a0`
- `0x6890`
- `0x14f00`
- `0x14f40`
- `0x155a0`
- `0x15b80`
- `0x15dc0`
- `0x16400`
- `0x16520`
- `0x165c0`
- `0x16ab0`
- `0x19180`
- `0x192e0`
- `0x194a0`
- `0x19630`
- `0x198d0`
- `0x19ab0`
- `0x19d10`
- `0x19e20`
- `0x1a3a0`
- `0x1a520`
- `0x1a7d0`
- `0x2e530`

## pseudocode

```c

```

## disassembly

```asm
0x51a0  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x51a5  stloc.0
0x51a6  ldloc.0
0x51a7  ldarg.0
0x51a8  stfld    class Microsoft.Crm.Workflow.ActivityHostBase <>c__DisplayClass15_0::<>4__this
0x51ad  ldloc.0
0x51ae  ldarg.1
0x51af  stfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x51b4  ldloc.0
0x51b5  ldarg.2
0x51b6  stfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x51bb  ldloc.0
0x51bc  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x51c1  ldloc.0
0x51c2  ldftn    instance void <>c__DisplayClass15_0::<AddHandlersAndExtensions>b__0(class [System.Activities]System.Activities.WorkflowApplicationCompletedEventArgs args)
0x51c8  newobj   instance void class [mscorlib]System.Action`1<class [System.Activities]System.Activities.WorkflowApplicationCompletedEventArgs>::.ctor(object, native int)
0x51cd  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::set_Completed(class [mscorlib]System.Action`1<class [System.Activities]System.Activities.WorkflowApplicationCompletedEventArgs>)
0x51d2  ldloc.0
0x51d3  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x51d8  ldloc.0
0x51d9  ldftn    instance valuetype [System.Activities]System.Activities.UnhandledExceptionAction <>c__DisplayClass15_0::<AddHandlersAndExtensions>b__1(class [System.Activities]System.Activities.WorkflowApplicationUnhandledExceptionEventArgs args)
0x51df  newobj   instance void class [mscorlib]System.Func`2<class [System.Activities]System.Activities.WorkflowApplicationUnhandledExceptionEventArgs, valuetype [System.Activities]System.Activities.UnhandledExceptionAction>::.ctor(object, native int)
0x51e4  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::set_OnUnhandledException(class [mscorlib]System.Func`2<class [System.Activities]System.Activities.WorkflowApplicationUnhandledExceptionEventArgs, valuetype [System.Activities]System.Activities.UnhandledExceptionAction>)
0x51e9  ldloc.0
0x51ea  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x51ef  ldloc.0
0x51f0  ldftn    instance void <>c__DisplayClass15_0::<AddHandlersAndExtensions>b__2(class [System.Activities]System.Activities.WorkflowApplicationAbortedEventArgs args)
0x51f6  newobj   instance void class [mscorlib]System.Action`1<class [System.Activities]System.Activities.WorkflowApplicationAbortedEventArgs>::.ctor(object, native int)
0x51fb  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::set_Aborted(class [mscorlib]System.Action`1<class [System.Activities]System.Activities.WorkflowApplicationAbortedEventArgs>)
0x5200  ldloc.0
0x5201  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x5206  ldloc.0
0x5207  ldftn    instance void <>c__DisplayClass15_0::<AddHandlersAndExtensions>b__3(class [System.Activities]System.Activities.WorkflowApplicationIdleEventArgs args)
0x520d  newobj   instance void class [mscorlib]System.Action`1<class [System.Activities]System.Activities.WorkflowApplicationIdleEventArgs>::.ctor(object, native int)
0x5212  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::set_Idle(class [mscorlib]System.Action`1<class [System.Activities]System.Activities.WorkflowApplicationIdleEventArgs>)
0x5217  ldloc.0
0x5218  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x521d  ldloc.0
0x521e  ldftn    instance void <>c__DisplayClass15_0::<AddHandlersAndExtensions>b__4(class [System.Activities]System.Activities.WorkflowApplicationEventArgs args)
0x5224  newobj   instance void class [mscorlib]System.Action`1<class [System.Activities]System.Activities.WorkflowApplicationEventArgs>::.ctor(object, native int)
0x5229  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::set_Unloaded(class [mscorlib]System.Action`1<class [System.Activities]System.Activities.WorkflowApplicationEventArgs>)
0x522e  ldloc.0
0x522f  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x5234  ldsfld   class [mscorlib]System.Func`2<class [System.Activities]System.Activities.WorkflowApplicationIdleEventArgs, valuetype [System.Activities]System.Activities.PersistableIdleAction> <>c::<>9__15_5
0x5239  dup
0x523a  brtrue.s loc_5253
0x523c  pop
0x523d  ldsfld   class <>c <>c::<>9
0x5242  ldftn    instance valuetype [System.Activities]System.Activities.PersistableIdleAction <>c::<AddHandlersAndExtensions>b__15_5(class [System.Activities]System.Activities.WorkflowApplicationIdleEventArgs args)
0x5248  newobj   instance void class [mscorlib]System.Func`2<class [System.Activities]System.Activities.WorkflowApplicationIdleEventArgs, valuetype [System.Activities]System.Activities.PersistableIdleAction>::.ctor(object, native int)
0x524d  dup
0x524e  stsfld   class [mscorlib]System.Func`2<class [System.Activities]System.Activities.WorkflowApplicationIdleEventArgs, valuetype [System.Activities]System.Activities.PersistableIdleAction> <>c::<>9__15_5
0x5253  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::set_PersistableIdle(class [mscorlib]System.Func`2<class [System.Activities]System.Activities.WorkflowApplicationIdleEventArgs, valuetype [System.Activities]System.Activities.PersistableIdleAction>)
0x5258  ldloc.0
0x5259  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x525e  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x5263  ldloc.0
0x5264  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x5269  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x526e  ldloc.0
0x526f  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x5274  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x5279  ldarg.0
0x527a  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ICrmServiceFactory Microsoft.Crm.Workflow.ActivityHostBase::_crmServiceFactory
0x527f  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x5284  ldloc.0
0x5285  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x528a  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x528f  newobj   instance void Microsoft.Crm.Workflow.Services.ExecutionPointersService::.ctor()
0x5294  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x5299  ldloc.0
0x529a  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x529f  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x52a4  ldloc.0
0x52a5  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x52aa  callvirt instance class Microsoft.Crm.Workflow.WorkflowTracingService Microsoft.Crm.Workflow.ICommonWorkflowContext::get_WorkflowTracingService()
0x52af  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x52b4  ldloc.0
0x52b5  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x52ba  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x52bf  ldloc.0
0x52c0  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x52c5  newobj   instance void Microsoft.Crm.Workflow.Services.AssignActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x52ca  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x52cf  ldloc.0
0x52d0  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x52d5  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x52da  ldloc.0
0x52db  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x52e0  newobj   instance void Microsoft.Crm.Workflow.Services.CreateActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x52e5  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x52ea  ldloc.0
0x52eb  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x52f0  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x52f5  ldloc.0
0x52f6  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x52fb  newobj   instance void Microsoft.Crm.Workflow.Services.RetrieveActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x5300  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x5305  ldloc.0
0x5306  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x530b  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x5310  ldloc.0
0x5311  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x5316  newobj   instance void Microsoft.Crm.Workflow.Services.SendEmailFromTemplateActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x531b  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x5320  ldloc.0
0x5321  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x5326  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x532b  ldloc.0
0x532c  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x5331  newobj   instance void Microsoft.Crm.Workflow.Services.SendEmailActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x5336  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x533b  ldloc.0
0x533c  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x5341  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x5346  ldloc.0
0x5347  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x534c  newobj   instance void Microsoft.Crm.Workflow.Services.SetStateActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x5351  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x5356  ldloc.0
0x5357  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x535c  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x5361  ldloc.0
0x5362  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x5367  newobj   instance void Microsoft.Crm.Workflow.Services.UpdateActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x536c  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x5371  ldloc.0
0x5372  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x5377  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x537c  ldloc.0
0x537d  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x5382  newobj   instance void Microsoft.Crm.Workflow.Services.ChildWorkflowActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x5387  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x538c  ldloc.0
0x538d  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x5392  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x5397  ldloc.0
0x5398  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x539d  newobj   instance void Microsoft.Crm.Workflow.Services.ConditionBranchService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x53a2  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x53a7  ldloc.0
0x53a8  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x53ad  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x53b2  ldloc.0
0x53b3  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x53b8  newobj   instance void Microsoft.Crm.Workflow.Services.ConditionActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x53bd  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x53c2  ldloc.0
0x53c3  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x53c8  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x53cd  ldloc.0
0x53ce  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x53d3  newobj   instance void Microsoft.Crm.Workflow.Services.WorkflowService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x53d8  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x53dd  ldloc.0
0x53de  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x53e3  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x53e8  ldloc.0
0x53e9  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x53ee  newobj   instance void Microsoft.Crm.Workflow.Services.CompositeActivityService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x53f3  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x53f8  ldloc.0
0x53f9  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x53fe  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x5403  ldloc.0
0x5404  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x5409  newobj   instance void Microsoft.Crm.Workflow.Services.ActivityReferenceService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x540e  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x5413  ldloc.0
0x5414  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x5419  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x541e  ldloc.0
0x541f  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x5424  newobj   instance void Microsoft.Crm.Workflow.Services.WebActivityReferenceService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x5429  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x542e  ldloc.0
0x542f  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x5434  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x5439  ldloc.0
0x543a  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x543f  newobj   instance void Microsoft.Crm.Workflow.Services.InvokeSdkMessageService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x5444  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x5449  ldloc.0
0x544a  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x544f  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x5454  ldloc.0
0x5455  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x545a  newobj   instance void Microsoft.Crm.Workflow.Services.SetAttributeValueService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x545f  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x5464  ldloc.0
0x5465  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x546a  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x546f  ldloc.0
0x5470  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x5475  newobj   instance void Microsoft.Crm.Workflow.Services.SetDefaultValueService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x547a  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x547f  ldloc.0
0x5480  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x5485  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x548a  ldloc.0
0x548b  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x5490  newobj   instance void Microsoft.Crm.Workflow.Services.SetMessageService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x5495  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x549a  ldloc.0
0x549b  ldfld    class [System.Activities]System.Activities.WorkflowApplication <>c__DisplayClass15_0::activityInstance
0x54a0  callvirt instance class [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager [System.Activities]System.Activities.WorkflowApplication::get_Extensions()
0x54a5  ldloc.0
0x54a6  ldfld    class Microsoft.Crm.Workflow.ICommonWorkflowContext <>c__DisplayClass15_0::context
0x54ab  newobj   instance void Microsoft.Crm.Workflow.Services.SetFieldRequiredLevelService::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x54b0  callvirt instance void [System.Activities]System.Activities.Hosting.WorkflowInstanceExtensionManager::Add(object)
0x54b5  ret
```
