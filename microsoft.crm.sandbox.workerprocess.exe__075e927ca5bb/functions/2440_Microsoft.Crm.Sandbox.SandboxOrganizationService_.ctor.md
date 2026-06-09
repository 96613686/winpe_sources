# Microsoft.Crm.Sandbox.SandboxOrganizationService::.ctor

- ea: `0x2440`
- end: `0x247b`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationService::.ctor`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x29f0`

## callees

- `0x1ec0`

## string_xrefs

- `0x2450`: `SandboxOrganizationService ctor`
- `0x2461`: `SandboxOrganizationService ctor: _listenerUri: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2440  ldarg.0
0x2441  ldarg.1
0x2442  ldarg.2
0x2443  ldarg.3
0x2444  ldarg.s  4
0x2446  ldarg.s  5
0x2448  ldarg.s  6
0x244a  call     instance void Microsoft.Crm.Sandbox.SandboxCallbackService::.ctor(string assemblyName, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext sdkContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter, int32 leaseTime)
0x244f  ldarg.2
0x2450  ldstr    aSandboxorganiz_0// "SandboxOrganizationService ctor"
0x2455  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::Trace(string)
0x245a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x245f  ldc.i4.s 0x26
0x2461  ldstr    aSandboxorganiz_1// "SandboxOrganizationService ctor: _liste"...
0x2466  ldc.i4.1
0x2467  newarr   [mscorlib]System.Object
0x246c  dup
0x246d  ldc.i4.0
0x246e  ldarg.0
0x246f  ldfld    string Microsoft.Crm.Sandbox.SandboxCallbackService::listenerUri
0x2474  stelem.ref
0x2475  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x247a  ret
```
