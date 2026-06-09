# Microsoft.Crm.Sandbox.SandboxAppDomainManager::Execute

- ea: `0x1d80`
- end: `0x1df8`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainManager::Execute`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1c40`
- `0x1ce0`

## callees

- `0x1d80`
- `0x1e00`
- `0x3090`
- `0x3630`
- `0x3a30`

## pseudocode

```c

```

## disassembly

```asm
0x1d80  newobj   instance void Microsoft.Crm.Sandbox.SandboxWorker::.ctor()
0x1d85  stloc.0
0x1d86  ldarg.2
0x1d87  brfalse.s loc_1DAD
0x1d89  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCustomActivityExecutionContext Microsoft.Crm.Sandbox.SandboxAppDomainManager::GetSampleActivityRequest()
0x1d8e  stloc.2
0x1d8f  ldloc.0
0x1d90  ldarg.0
0x1d91  ldloc.2
0x1d92  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d97  ldc.i4.0
0x1d98  ldstr    aMicrosoftCrmSa_7// "Microsoft.Crm.Sandbox"
0x1d9d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1da2  ldarg.1
0x1da3  ldloca.s 1
0x1da5  ldc.i4.0
0x1da6  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCustomActivityExecutionContext Microsoft.Crm.Sandbox.SandboxWorker::ExecuteCustomWorkflowActivity(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCustomActivityExecutionContext requestContext, valuetype [mscorlib]System.Guid pluginAssemblyId, int32 sourceHash, string assemblyName, valuetype [mscorlib]System.Guid pluginTypeId, string pluginTypeName, [out] class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter& workerCounter, bool returnTraceInfo)
0x1dab  pop
0x1dac  ret
0x1dad  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext::.ctor()
0x1db2  stloc.3
0x1db3  ldloc.3
0x1db4  ldstr    aTest// "test"
0x1db9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string)
0x1dbe  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::set_OwningExtension(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x1dc3  ldloc.3
0x1dc4  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::SerializeForTransmit()
0x1dc9  ldloc.3
0x1dca  ldnull
0x1dcb  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::set_OwningExtension(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x1dd0  ldloc.0
0x1dd1  ldarg.0
0x1dd2  ldloc.3
0x1dd3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1dd8  ldc.i4.0
0x1dd9  ldstr    aMicrosoftCrmSa_7// "Microsoft.Crm.Sandbox"
0x1dde  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1de3  ldarg.1
0x1de4  ldsfld   string [mscorlib]System.String::Empty
0x1de9  ldsfld   string [mscorlib]System.String::Empty
0x1dee  ldloca.s 1
0x1df0  ldc.i4.0
0x1df1  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext Microsoft.Crm.Sandbox.SandboxWorker::Execute(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext requestContext, valuetype [mscorlib]System.Guid pluginAssemblyId, int32 sourceHash, string assemblyName, valuetype [mscorlib]System.Guid pluginTypeId, string pluginTypeName, string pluginConfiguration, string pluginSecureConfig, [out] class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter& workerCounter, bool returnTraceInfo)
0x1df6  pop
0x1df7  ret
```
