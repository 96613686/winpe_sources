# Microsoft.Crm.Sandbox.SandboxWorkerProcess::ExecuteCustomWorkflowActivity

- ea: `0xb140`
- end: `0xb1c1`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::ExecuteCustomWorkflowActivity`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xbf70`

## callees

- `0xa810`
- `0xa920`
- `0xae00`
- `0xaf80`
- `0xb140`

## string_xrefs

- `0xb17b`: `WorkerCommunication`

## pseudocode

```c

```

## disassembly

```asm
0xb140  ldarg.0
0xb141  ldarg.1
0xb142  ldarg.2
0xb143  ldarg.s  5
0xb145  ldarg.s  6
0xb147  ldarg.s  7
0xb149  call     instance class [mscorlib]System.Tuple`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord, class Microsoft.Crm.Sandbox.SandboxWorkerClient> Microsoft.Crm.Sandbox.SandboxWorkerProcess::Initialize(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext requestContext, string assemblyName, valuetype [mscorlib]System.Guid pluginTypeId, string pluginTypeName)
0xb14e  dup
0xb14f  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord, class Microsoft.Crm.Sandbox.SandboxWorkerClient>::get_Item1()
0xb154  stloc.1
0xb155  dup
0xb156  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord, class Microsoft.Crm.Sandbox.SandboxWorkerClient>::get_Item2()
0xb15b  stloc.2
0xb15c  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord, class Microsoft.Crm.Sandbox.SandboxWorkerClient>::get_Item3()
0xb161  stloc.3
0xb162  ldarg.1
0xb163  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0xb168  stloc.s  4
0xb16a  ldarg.0
0xb16b  ldloc.1
0xb16c  ldloc.3
0xb16d  ldloc.2
0xb16e  ldarg.2
0xb16f  ldarg.s  5
0xb171  ldarg.s  7
0xb173  ldarg.3
0xb174  ldarg.s  6
0xb176  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TrackCall(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, class Microsoft.Crm.Sandbox.SandboxWorkerClient workerClient, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord pluginExecutionRecord, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext requestContext, string assemblyName, string pluginTypeName, valuetype [mscorlib]System.Guid pluginAssemblyId, valuetype [mscorlib]System.Guid pluginTypeId)
0xb17b  ldstr    aWorkercommunic// "WorkerCommunication"
0xb180  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.ChaosAgent::ChaosClientCall(string)
0xb185  ldloc.3
0xb186  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_Proxy()
0xb18b  ldloc.s  4
0xb18d  ldarg.2
0xb18e  ldarg.3
0xb18f  ldarg.s  4
0xb191  ldarg.s  5
0xb193  ldarg.s  6
0xb195  ldarg.s  7
0xb197  ldloca.s 5
0xb199  ldarg.s  8
0xb19b  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCustomActivityExecutionContext [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker::ExecuteCustomWorkflowActivity(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCustomActivityExecutionContext, valuetype [mscorlib]System.Guid, int32, string, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter&, bool)
0xb1a0  stloc.0
0xb1a1  ldarg.0
0xb1a2  ldloc.1
0xb1a3  ldarg.2
0xb1a4  ldloc.s  5
0xb1a6  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TrackGoodReturn(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext requestContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter)
0xb1ab  leave.s  loc_B1BF
0xb1ad  stloc.s  6
0xb1af  ldarg.0
0xb1b0  ldloc.s  6
0xb1b2  ldarg.2
0xb1b3  ldloc.3
0xb1b4  ldloc.1
0xb1b5  ldloc.2
0xb1b6  ldloc.s  4
0xb1b8  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::HandleException(class [mscorlib]System.Exception e, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext requestContext, class Microsoft.Crm.Sandbox.SandboxWorkerClient workerClient, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord pluginExecutionRecord, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo)
0xb1bd  rethrow
0xb1bf  ldloc.0
0xb1c0  ret
```
