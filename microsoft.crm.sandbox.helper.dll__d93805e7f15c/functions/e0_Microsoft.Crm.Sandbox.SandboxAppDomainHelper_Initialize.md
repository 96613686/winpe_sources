# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::Initialize

- ea: `0xe0`
- end: `0x167`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::Initialize`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xe0`
- `0x1990`
- `0x1b40`

## pseudocode

```c

```

## disassembly

```asm
0xe0  ldarg.s  4
0xe2  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::set_TracingService(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService value)
0xe7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xec  ldc.i4.3
0xed  ldstr    aSandboxappdoma// "SandboxAppDomainHelper.Initialize: ente"...
0xf2  ldnull
0xf3  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0xf8  ldsfld   string Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_crashFile
0xfd  brfalse.s loc_10A
0xff  ldstr    aCrmSandboxInte// "CRM Sandbox Internal Error: _crashFile"
0x104  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x109  throw
0x10a  ldarg.3
0x10b  stsfld   string Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_crashFile
0x110  ldarg.0
0x111  ldarg.2
0x112  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_organizationId
0x117  ldc.i4   0xFF0
0x11c  call     void [System]System.Net.ServicePointManager::set_SecurityProtocol(valuetype [System]System.Net.SecurityProtocolType)
0x121  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x126  ldnull
0x127  ldftn    void Microsoft.Crm.Sandbox.SandboxAppDomainHelper::UnhandledExceptionHandler(object sender, class [mscorlib]System.UnhandledExceptionEventArgs e)
0x12d  newobj   instance void [mscorlib]System.UnhandledExceptionEventHandler::.ctor(object, native int)
0x132  callvirt instance void [mscorlib]System.AppDomain::add_UnhandledException(class [mscorlib]System.UnhandledExceptionEventHandler)
0x137  ldarg.1
0x138  brfalse.s loc_15A
0x13a  ldsfld   class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceContext/SequentialGuidOverrideDelegate [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SequentialGuidOverride
0x13f  ldarg.0
0x140  ldftn    instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomainHelper::NamedPipeSequentialGuid()
0x146  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceContext/SequentialGuidOverrideDelegate::.ctor(object, native int)
0x14b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x150  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceContext/SequentialGuidOverrideDelegate
0x155  stsfld   class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceContext/SequentialGuidOverrideDelegate [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SequentialGuidOverride
0x15a  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WhoAmIRequest::.ctor()
0x15f  pop
0x160  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WhoAmIResponse::.ctor()
0x165  pop
0x166  ret
```
