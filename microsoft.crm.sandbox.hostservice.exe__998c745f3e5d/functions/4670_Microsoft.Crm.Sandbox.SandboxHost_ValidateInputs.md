# Microsoft.Crm.Sandbox.SandboxHost::ValidateInputs

- ea: `0x4670`
- end: `0x4792`
- name: `Microsoft.Crm.Sandbox.SandboxHost::ValidateInputs`
- size: `290`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xba70`
- `0xbf70`

## callees

- `0x3320`
- `0x4670`
- `0x49d0`
- `0x6340`

## string_xrefs

- `0x4696`: `owningExtension`
- `0x46a1`: `pluginAssemblyId`
- `0x46c8`: `pluginTypeId`
- `0x46d4`: `pluginTypeName`
- `0x476a`: `The Sandbox Host has not completed initialization`

## pseudocode

```c

```

## disassembly

```asm
0x4670  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::EnterExecute()
0x4675  call     void Microsoft.Crm.Sandbox.SandboxHost::AuthenticateCaller()
0x467a  ldarg.1
0x467b  ldstr    aCallinfo// "callInfo"
0x4680  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4685  ldarg.2
0x4686  ldstr    aRequestcontext// "requestContext"
0x468b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4690  ldarg.2
0x4691  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x4696  ldstr    aOwningextensio// "owningExtension"
0x469b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x46a0  ldarg.3
0x46a1  ldstr    aPluginassembly// "pluginAssemblyId"
0x46a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x46ab  ldarg.s  4
0x46ad  ldc.i4.0
0x46ae  cgt.un
0x46b0  ldstr    aSourcehash// "sourceHash"
0x46b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x46ba  ldarg.s  5
0x46bc  ldstr    aAssemblyname// "assemblyName"
0x46c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x46c6  ldarg.s  6
0x46c8  ldstr    aPlugintypeid// "pluginTypeId"
0x46cd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x46d2  ldarg.s  7
0x46d4  ldstr    aPlugintypename// "pluginTypeName"
0x46d9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x46de  ldarg.1
0x46df  ldstr    aIsandboxhostEx// "ISandboxHost.Execute"
0x46e4  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::Trace(string)
0x46e9  ldarg.s  9
0x46eb  ldarg.2
0x46ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x46f1  ldarg.s  5
0x46f3  ldarg.s  7
0x46f5  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::AdditionalData(valuetype [mscorlib]System.Guid, string, string)
0x46fa  ldarg.s  9
0x46fc  ldarg.2
0x46fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x4702  ldarg.1
0x4703  ldarg.2
0x4704  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x4709  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Enter(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, int32)
0x470e  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxHost::_executeCount
0x4713  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x4718  pop
0x4719  ldc.i4.s 0xD3
0x471b  stloc.0
0x471c  ldsfld   bool Microsoft.Crm.Sandbox.SandboxHost::_shutdownFlag
0x4721  brfalse.s loc_474E
0x4723  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4728  stloc.2
0x4729  ldloca.s 2
0x472b  ldloc.0
0x472c  conv.r8
0x472d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x4732  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxHost::_shutdownTime
0x4737  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x473c  brfalse.s loc_474E
0x473e  ldstr    aTheSandboxHost// "The Sandbox Host is shutting down"
0x4743  ldc.i4   0x8004418E
0x4748  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmSandboxStartStopException::.ctor(string, int32)
0x474d  throw
0x474e  ldarg.3
0x474f  ldarg.s  4
0x4751  ldarg.s  8
0x4753  ldarg.2
0x4754  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x4759  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::CheckAssembly(valuetype [mscorlib]System.Guid pluginAssemblyId, int32 pluginAssemblyHashCode, string pluginAssemblyContents, valuetype [mscorlib]System.Guid organizationId)
0x475e  ldc.i4.0
0x475f  stloc.1
0x4760  br.s     loc_4784
0x4762  ldloc.1
0x4763  dup
0x4764  ldc.i4.1
0x4765  add
0x4766  stloc.1
0x4767  ldc.i4.5
0x4768  ble.s    loc_477A
0x476a  ldstr    aTheSandboxHost_0// "The Sandbox Host has not completed init"...
0x476f  ldc.i4   0x8004418E
0x4774  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmSandboxStartStopException::.ctor(string, int32)
0x4779  throw
0x477a  ldc.i4   0x3E8
0x477f  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x4784  ldarg.1
0x4785  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x478a  call     bool Microsoft.Crm.Sandbox.SandboxWorkerManager::Started(bool useDrawbridge)
0x478f  brfalse.s loc_4762
0x4791  ret
```
