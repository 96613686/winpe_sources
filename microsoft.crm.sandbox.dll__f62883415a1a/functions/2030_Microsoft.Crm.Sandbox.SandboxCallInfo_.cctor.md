# Microsoft.Crm.Sandbox.SandboxCallInfo::.cctor

- ea: `0x2030`
- end: `0x217a`
- name: `Microsoft.Crm.Sandbox.SandboxCallInfo::.cctor`
- size: `330`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x14d0`
- `0x2030`
- `0x30e0`

## string_xrefs

- `0x2150`: `MSCRMAsyncService`
- `0x2137`: `CrmScaleGroupProvisioningService`
- `0x2144`: `CrmScaleGroupProvisioningService`
- `0x2161`: `SandboxCallInfo: _serviceClassForServerPrincipalName: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2030  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x2035  stloc.0
0x2036  ldloc.0
0x2037  callvirt instance string [System]System.Diagnostics.Process::get_ProcessName()
0x203c  stsfld   string Microsoft.Crm.Sandbox.SandboxCallInfo::_cachedProcessName
0x2041  ldloc.0
0x2042  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x2047  stsfld   int32 Microsoft.Crm.Sandbox.SandboxCallInfo::_cachedProcessId
0x204c  leave.s  loc_2058
0x204e  ldloc.0
0x204f  brfalse.s loc_2057
0x2051  ldloc.0
0x2052  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2057  endfinally
0x2058  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x205d  callvirt instance int32 [mscorlib]System.AppDomain::get_Id()
0x2062  stsfld   int32 Microsoft.Crm.Sandbox.SandboxCallInfo::_cachedAppDomainId
0x2067  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x206c  ldc.i4.s 0x26
0x206e  ldstr    aSandboxcallinf// "SandboxCallInfo static ctor"
0x2073  ldc.i4.0
0x2074  newarr   [mscorlib]System.Object
0x2079  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x207e  call     bool Microsoft.Crm.Sandbox.SandboxUtility::get_IsSandboxClientProcess()
0x2083  brfalse  loc_2179
0x2088  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x208d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x2092  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCallInfo::_cachedScaleGroupId
0x2097  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x209c  ldc.i4.s 0x26
0x209e  ldstr    aSandboxcallinf_0// "SandboxCallInfo: _scaleGroupId: {0}"
0x20a3  ldc.i4.1
0x20a4  newarr   [mscorlib]System.Object
0x20a9  dup
0x20aa  ldc.i4.0
0x20ab  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCallInfo::_cachedScaleGroupId
0x20b0  box      [mscorlib]System.Guid
0x20b5  stelem.ref
0x20b6  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x20bb  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0x20c0  stloc.1
0x20c1  ldloc.1
0x20c2  ldstr    aCurrentidentit// "currentIdentity"
0x20c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x20cc  ldloc.1
0x20cd  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x20d2  ldstr    aCurrentidentit_0// "currentIdentity.User"
0x20d7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x20dc  ldloc.1
0x20dd  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x20e2  ldc.i4.s 0x18
0x20e4  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x20e9  brtrue.s loc_20FA
0x20eb  ldloc.1
0x20ec  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x20f1  ldc.i4.s 0x17
0x20f3  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x20f8  brfalse.s loc_2113
0x20fa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20ff  ldc.i4.s 0x26
0x2101  ldstr    aSandboxcallinf_1// "SandboxCallInfo: system account - no SP"...
0x2106  ldc.i4.0
0x2107  newarr   [mscorlib]System.Object
0x210c  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x2111  leave.s  loc_2179
0x2113  leave.s  loc_211F
0x2115  ldloc.1
0x2116  brfalse.s loc_211E
0x2118  ldloc.1
0x2119  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x211e  endfinally
0x211f  call     bool [System.Web]System.Web.Hosting.HostingEnvironment::get_IsHosted()
0x2124  brfalse.s loc_2132
0x2126  ldstr    aHttp_0// "HTTP"
0x212b  stsfld   string Microsoft.Crm.Sandbox.SandboxCallInfo::_cachedServiceClassForServerPrincipalName
0x2130  br.s     loc_215A
0x2132  ldsfld   string Microsoft.Crm.Sandbox.SandboxCallInfo::_cachedProcessName
0x2137  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x213c  ldc.i4.5
0x213d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2142  brfalse.s loc_2150
0x2144  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x2149  stsfld   string Microsoft.Crm.Sandbox.SandboxCallInfo::_cachedServiceClassForServerPrincipalName
0x214e  br.s     loc_215A
0x2150  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0x2155  stsfld   string Microsoft.Crm.Sandbox.SandboxCallInfo::_cachedServiceClassForServerPrincipalName
0x215a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x215f  ldc.i4.s 0x26
0x2161  ldstr    aSandboxcallinf_2// "SandboxCallInfo: _serviceClassForServer"...
0x2166  ldc.i4.1
0x2167  newarr   [mscorlib]System.Object
0x216c  dup
0x216d  ldc.i4.0
0x216e  ldsfld   string Microsoft.Crm.Sandbox.SandboxCallInfo::_cachedServiceClassForServerPrincipalName
0x2173  stelem.ref
0x2174  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x2179  ret
```
