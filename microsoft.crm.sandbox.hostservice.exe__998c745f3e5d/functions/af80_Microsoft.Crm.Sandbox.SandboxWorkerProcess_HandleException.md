# Microsoft.Crm.Sandbox.SandboxWorkerProcess::HandleException

- ea: `0xaf80`
- end: `0xb089`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::HandleException`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xa960`
- `0xb140`

## callees

- `0xaf80`
- `0xb090`

## pseudocode

```c

```

## disassembly

```asm
0xaf80  ldarg.0
0xaf81  ldflda   int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_activeWorkerExecuteCount
0xaf86  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0xaf8b  pop
0xaf8c  ldarg.s  6
0xaf8e  ldarg.s  5
0xaf90  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_PluginAssemblyName()
0xaf95  ldstr    asc_1B5EA// ":"
0xaf9a  ldarg.s  5
0xaf9c  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_PluginTypeName()
0xafa1  call     string [mscorlib]System.String::Concat(string, string, string)
0xafa6  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::set_PluginInfo(string)
0xafab  ldarg.1
0xafac  callvirt instance string [mscorlib]System.Object::ToString()
0xafb1  stloc.0
0xafb2  ldarg.2
0xafb3  brtrue.s loc_AFBD
0xafb5  ldsfld   string [mscorlib]System.String::Empty
0xafba  pop
0xafbb  br.s     loc_AFD2
0xafbd  ldarg.2
0xafbe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0xafc3  stloc.3
0xafc4  ldloca.s 3
0xafc6  constrained. [mscorlib]System.Guid
0xafcc  callvirt instance string [mscorlib]System.Object::ToString()
0xafd1  pop
0xafd2  ldarg.2
0xafd3  brtrue.s loc_AFDD
0xafd5  ldsfld   string [mscorlib]System.String::Empty
0xafda  pop
0xafdb  br.s     loc_AFFB
0xafdd  ldarg.2
0xafde  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_RequestId()
0xafe3  stloc.s  4
0xafe5  ldloca.s 4
0xafe7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0xafec  stloc.3
0xafed  ldloca.s 3
0xafef  constrained. [mscorlib]System.Guid
0xaff5  callvirt instance string [mscorlib]System.Object::ToString()
0xaffa  pop
0xaffb  ldarg.s  4
0xaffd  ldarg.1
0xaffe  ldc.i4.0
0xafff  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::BadReturn(class [mscorlib]System.Exception, bool)
0xb004  ldarg.1
0xb005  ldarg.2
0xb006  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xb00b  ldarg.3
0xb00c  ldarg.s  6
0xb00e  ldloca.s 2
0xb010  ldloca.s 0
0xb012  call     bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::ConvertFaultException(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.Sandbox.SandboxWorkerClient workerClient, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, [out] class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>& newFaultException, string& exceptionMessage)
0xb017  stloc.1
0xb018  ldnull
0xb019  ldarg.2
0xb01a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xb01f  ldc.i4.s 0x21
0xb021  ldstr    aSandboxworkerp_40// "SandboxWorkerProcess.Execute: Execute f"...
0xb026  ldc.i4.5
0xb027  newarr   [mscorlib]System.Object
0xb02c  dup
0xb02d  ldc.i4.0
0xb02e  ldarg.0
0xb02f  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xb034  stelem.ref
0xb035  dup
0xb036  ldc.i4.1
0xb037  ldarg.3
0xb038  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_ClientId()
0xb03d  stelem.ref
0xb03e  dup
0xb03f  ldc.i4.2
0xb040  ldarg.2
0xb041  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xb046  box      [mscorlib]System.Guid
0xb04b  stelem.ref
0xb04c  dup
0xb04d  ldc.i4.3
0xb04e  ldloc.0
0xb04f  stelem.ref
0xb050  dup
0xb051  ldc.i4.4
0xb052  ldarg.s  6
0xb054  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::GetCallInfoHierarchy(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0xb059  stelem.ref
0xb05a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb05f  ldloc.1
0xb060  brfalse.s loc_B06B
0xb062  ldarg.s  5
0xb064  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter::RequestBad()
0xb069  br.s     loc_B072
0xb06b  ldarg.s  5
0xb06d  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter::RequestGood()
0xb072  ldloc.2
0xb073  brfalse.s loc_B088
0xb075  ldloc.2
0xb076  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0xb07b  ldarg.1
0xb07c  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsSafeToRetry(class [mscorlib]System.Exception)
0xb081  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::set_ExceptionRetriable(bool)
0xb086  ldloc.2
0xb087  throw
0xb088  ret
```
