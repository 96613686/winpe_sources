# Microsoft.Crm.Sandbox.SandboxHost::CheckIfHostShouldFailAndDiscardWorker

- ea: `0x4130`
- end: `0x420c`
- name: `Microsoft.Crm.Sandbox.SandboxHost::CheckIfHostShouldFailAndDiscardWorker`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xba70`
- `0xbf70`

## callees

- `0x4130`
- `0x4210`
- `0x9de0`

## string_xrefs

- `0x4179`: `SandboxHost.ExecuteAndReturnTraceInfo: Attempt {0} of {1}. Retrying. Error: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x4130  ldarg.2
0x4131  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsSafeToRetry(class [mscorlib]System.Exception)
0x4136  stloc.0
0x4137  ldloc.0
0x4138  brfalse.s loc_4162
0x413a  ldarg.2
0x413b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x4140  ldc.i4.s 0x2D
0x4142  ldstr    aSandboxhostExe// "SandboxHost.ExecuteAndReturnTraceInfo: "...
0x4147  ldc.i4.1
0x4148  newarr   [mscorlib]System.Object
0x414d  dup
0x414e  ldc.i4.0
0x414f  ldarg.2
0x4150  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::ExpandException(class [mscorlib]System.Exception)
0x4155  stelem.ref
0x4156  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x415b  ldarg.1
0x415c  ldc.i4.3
0x415d  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0x4162  ldarg.3
0x4163  ldarg.0
0x4164  call     instance int32 Microsoft.Crm.Sandbox.SandboxHost::get_MaxWorkerCallRetry()
0x4169  ldc.i4.1
0x416a  sub
0x416b  clt
0x416d  ldloc.0
0x416e  and
0x416f  brfalse.s loc_41B3
0x4171  ldarg.2
0x4172  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x4177  ldc.i4.s 0x2D
0x4179  ldstr    aSandboxhostExe_0// "SandboxHost.ExecuteAndReturnTraceInfo: "...
0x417e  ldc.i4.3
0x417f  newarr   [mscorlib]System.Object
0x4184  dup
0x4185  ldc.i4.0
0x4186  ldarg.3
0x4187  ldc.i4.1
0x4188  add
0x4189  box      [mscorlib]System.Int32
0x418e  stelem.ref
0x418f  dup
0x4190  ldc.i4.1
0x4191  ldarg.0
0x4192  call     instance int32 Microsoft.Crm.Sandbox.SandboxHost::get_MaxWorkerCallRetry()
0x4197  box      [mscorlib]System.Int32
0x419c  stelem.ref
0x419d  dup
0x419e  ldc.i4.2
0x419f  ldarg.2
0x41a0  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::ExpandException(class [mscorlib]System.Exception)
0x41a5  stelem.ref
0x41a6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x41ab  ldarg.3
0x41ac  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::ExponentialBackOffInMilliseconds(int32)
0x41b1  ldc.i4.0
0x41b2  ret
0x41b3  ldarg.2
0x41b4  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x41b9  stloc.1
0x41ba  ldloc.1
0x41bb  brfalse.s loc_420A
0x41bd  ldloc.1
0x41be  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x41c3  brfalse.s loc_420A
0x41c5  ldloc.1
0x41c6  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x41cb  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_OriginalException()
0x41d0  ldc.i4.s 0xA
0x41d2  stloc.2
0x41d3  ldloca.s 2
0x41d5  constrained. [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategory
0x41db  callvirt instance string [mscorlib]System.Object::ToString()
0x41e0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x41e5  brfalse.s loc_420A
0x41e7  ldarg.2
0x41e8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x41ed  ldc.i4.s 0x26
0x41ef  ldstr    aSandboxhostExe_1// "SandboxHost.ExecuteAndReturnTraceInfo: "...
0x41f4  ldc.i4.1
0x41f5  newarr   [mscorlib]System.Object
0x41fa  dup
0x41fb  ldc.i4.0
0x41fc  ldarg.2
0x41fd  stelem.ref
0x41fe  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4203  ldarg.1
0x4204  ldc.i4.3
0x4205  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0x420a  ldc.i4.1
0x420b  ret
```
