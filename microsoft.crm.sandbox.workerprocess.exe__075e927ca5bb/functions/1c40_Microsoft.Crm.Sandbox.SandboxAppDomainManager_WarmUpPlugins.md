# Microsoft.Crm.Sandbox.SandboxAppDomainManager::WarmUpPlugins

- ea: `0x1c40`
- end: `0x1cd3`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainManager::WarmUpPlugins`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1b30`

## callees

- `0x1c40`
- `0x1d80`
- `0x35e0`

## string_xrefs

- `0x1c40`: `Microsoft.Crm.Sandbox.WarmUpFailureWithFaultExceptionPlugin`
- `0x1c4d`: `Microsoft.Crm.Sandbox.WarmUpFailureWithFaultExceptionPlugin`
- `0x1c63`: `Microsoft.Crm.Sandbox.WarmUpFailureWithFaultExceptionPlugin: Expected error on dry run: {0}`
- `0x1c89`: `Microsoft.Crm.Sandbox.WarmupSuccessPlugin`
- `0x1c96`: `Microsoft.Crm.Sandbox.WarmupSuccessPlugin`
- `0x1cac`: `Microsoft.Crm.Sandbox.WarmupSuccessPlugin: Expected error on dry run: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1c40  ldstr    aMicrosoftCrmSa// "Microsoft.Crm.Sandbox.WarmUpFailureWith"...
0x1c45  ldc.i4.1
0x1c46  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x1c4b  stloc.0
0x1c4c  ldarg.0
0x1c4d  ldstr    aMicrosoftCrmSa// "Microsoft.Crm.Sandbox.WarmUpFailureWith"...
0x1c52  ldc.i4.0
0x1c53  call     void Microsoft.Crm.Sandbox.SandboxAppDomainManager::Execute(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, string typeName, bool activity)
0x1c58  leave.s  loc_1C89
0x1c5a  stloc.1
0x1c5b  ldloc.1
0x1c5c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c61  ldc.i4.s 0x21
0x1c63  ldstr    aMicrosoftCrmSa_0// "Microsoft.Crm.Sandbox.WarmUpFailureWith"...
0x1c68  ldc.i4.1
0x1c69  newarr   [mscorlib]System.Object
0x1c6e  dup
0x1c6f  ldc.i4.0
0x1c70  ldloc.1
0x1c71  stelem.ref
0x1c72  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c77  leave.s  loc_1C89
0x1c79  call     void Microsoft.Crm.Sandbox.SandboxWorker::ResetWorkerFromColdStart()
0x1c7e  endfinally
0x1c7f  ldloc.0
0x1c80  brfalse.s loc_1C88
0x1c82  ldloc.0
0x1c83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c88  endfinally
0x1c89  ldstr    aMicrosoftCrmSa_1// "Microsoft.Crm.Sandbox.WarmupSuccessPlug"...
0x1c8e  ldc.i4.1
0x1c8f  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x1c94  stloc.0
0x1c95  ldarg.0
0x1c96  ldstr    aMicrosoftCrmSa_1// "Microsoft.Crm.Sandbox.WarmupSuccessPlug"...
0x1c9b  ldc.i4.0
0x1c9c  call     void Microsoft.Crm.Sandbox.SandboxAppDomainManager::Execute(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, string typeName, bool activity)
0x1ca1  leave.s  loc_1CD2
0x1ca3  stloc.2
0x1ca4  ldloc.2
0x1ca5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1caa  ldc.i4.s 0x21
0x1cac  ldstr    aMicrosoftCrmSa_2// "Microsoft.Crm.Sandbox.WarmupSuccessPlug"...
0x1cb1  ldc.i4.1
0x1cb2  newarr   [mscorlib]System.Object
0x1cb7  dup
0x1cb8  ldc.i4.0
0x1cb9  ldloc.2
0x1cba  stelem.ref
0x1cbb  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1cc0  leave.s  loc_1CD2
0x1cc2  call     void Microsoft.Crm.Sandbox.SandboxWorker::ResetWorkerFromColdStart()
0x1cc7  endfinally
0x1cc8  ldloc.0
0x1cc9  brfalse.s loc_1CD1
0x1ccb  ldloc.0
0x1ccc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cd1  endfinally
0x1cd2  ret
```
