# Microsoft.Crm.Sandbox.SandboxHostSids::IsCallerAllowed

- ea: `0x1d40`
- end: `0x1eba`
- name: `Microsoft.Crm.Sandbox.SandboxHostSids::IsCallerAllowed`
- size: `378`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1d40`
- `0x8d70`
- `0x8d90`

## string_xrefs

- `0x1dad`: `sidEntry`
- `0x1d83`: `SandboxHostSids.IsCallerAllowed: not found: {0}`
- `0x1dbf`: `expectedSid`
- `0x1dd3`: `expectedSidSddlForm`
- `0x1de4`: `SandboxHostSids.IsCallerAllowed: {0} expectedSidSddlForm: {1}`
- `0x1e36`: `SandboxHostSids.IsCallerAllowed: not authenticated: {0}`
- `0x1e6e`: `callerAccountSid`
- `0x1ea0`: `SandboxHostSids.IsCallerAllowed: unexpected sid: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1d40  ldarg.0
0x1d41  ldstr    aCallinfo// "callInfo"
0x1d46  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d4b  ldarg.0
0x1d4c  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_MachineName()
0x1d51  ldstr    aCallinfoMachin// "callInfo.MachineName"
0x1d56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1d5b  ldarg.1
0x1d5c  ldstr    asc_C3B0// "-"
0x1d61  stind.ref
0x1d62  ldarg.0
0x1d63  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_MachineName()
0x1d68  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x1d6d  stloc.0
0x1d6e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry> Microsoft.Crm.Sandbox.SandboxHostSids::_sids
0x1d73  ldloc.0
0x1d74  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry>::ContainsKey(var<u1>)
0x1d79  brtrue.s loc_1DA0
0x1d7b  ldnull
0x1d7c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d81  ldc.i4.s 0x28
0x1d83  ldstr    aSandboxhostsid_1// "SandboxHostSids.IsCallerAllowed: not fo"...
0x1d88  ldc.i4.1
0x1d89  newarr   [mscorlib]System.Object
0x1d8e  dup
0x1d8f  ldc.i4.0
0x1d90  ldloc.0
0x1d91  stelem.ref
0x1d92  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d97  ldarg.2
0x1d98  ldstr    aSandboxHostNot// "Sandbox Host Not Found"
0x1d9d  stind.ref
0x1d9e  ldc.i4.0
0x1d9f  ret
0x1da0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry> Microsoft.Crm.Sandbox.SandboxHostSids::_sids
0x1da5  ldloc.0
0x1da6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry>::get_Item(void)
0x1dab  stloc.1
0x1dac  ldloc.1
0x1dad  ldstr    aSidentry// "sidEntry"
0x1db2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1db7  ldloc.1
0x1db8  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier SidEntry::get_Sid()
0x1dbd  stloc.2
0x1dbe  ldloc.2
0x1dbf  ldstr    aExpectedsid// "expectedSid"
0x1dc4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1dc9  ldarg.1
0x1dca  ldloc.1
0x1dcb  callvirt instance string SidEntry::get_AccountName()
0x1dd0  stind.ref
0x1dd1  ldarg.1
0x1dd2  ldind.ref
0x1dd3  ldstr    aExpectedsidsdd// "expectedSidSddlForm"
0x1dd8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1ddd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1de2  ldc.i4.s 0x28
0x1de4  ldstr    aSandboxhostsid_2// "SandboxHostSids.IsCallerAllowed: {0} ex"...
0x1de9  ldc.i4.2
0x1dea  newarr   [mscorlib]System.Object
0x1def  dup
0x1df0  ldc.i4.0
0x1df1  ldloc.0
0x1df2  stelem.ref
0x1df3  dup
0x1df4  ldc.i4.1
0x1df5  ldarg.1
0x1df6  ldind.ref
0x1df7  stelem.ref
0x1df8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1dfd  call     class [System.ServiceModel]System.ServiceModel.ServiceSecurityContext [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_Current()
0x1e02  callvirt instance class [mscorlib]System.Security.Principal.WindowsIdentity [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_WindowsIdentity()
0x1e07  stloc.3
0x1e08  ldloc.3
0x1e09  ldstr    aCalleridentity// "callerIdentity"
0x1e0e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1e13  ldsfld   object Microsoft.Crm.Sandbox.SandboxHostSids::_lockObject
0x1e18  stloc.s  5
0x1e1a  ldc.i4.0
0x1e1b  stloc.s  6
0x1e1d  ldloc.s  5
0x1e1f  ldloca.s 6
0x1e21  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1e26  ldloc.3
0x1e27  callvirt instance bool [mscorlib]System.Security.Claims.ClaimsIdentity::get_IsAuthenticated()
0x1e2c  brtrue.s loc_1E56
0x1e2e  ldnull
0x1e2f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e34  ldc.i4.s 0x28
0x1e36  ldstr    aSandboxhostsid_3// "SandboxHostSids.IsCallerAllowed: not au"...
0x1e3b  ldc.i4.1
0x1e3c  newarr   [mscorlib]System.Object
0x1e41  dup
0x1e42  ldc.i4.0
0x1e43  ldloc.0
0x1e44  stelem.ref
0x1e45  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e4a  ldarg.2
0x1e4b  ldstr    aNotAuthenticat// "Not Authenticated"
0x1e50  stind.ref
0x1e51  ldc.i4.0
0x1e52  stloc.s  7
0x1e54  leave.s  loc_1EB7
0x1e56  leave.s  loc_1E64
0x1e58  ldloc.s  6
0x1e5a  brfalse.s loc_1E63
0x1e5c  ldloc.s  5
0x1e5e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1e63  endfinally
0x1e64  ldloc.3
0x1e65  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x1e6a  stloc.s  4
0x1e6c  ldloc.s  4
0x1e6e  ldstr    aCalleraccounts// "callerAccountSid"
0x1e73  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1e78  ldarg.2
0x1e79  ldloc.3
0x1e7a  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x1e7f  ldstr    asc_C5D2// ";"
0x1e84  ldloc.s  4
0x1e86  call     string [mscorlib]System.String::Concat(object, object, object)
0x1e8b  stind.ref
0x1e8c  ldloc.s  4
0x1e8e  ldloc.2
0x1e8f  call     bool [mscorlib]System.Security.Principal.SecurityIdentifier::op_Equality(class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x1e94  brfalse.s loc_1E98
0x1e96  ldc.i4.1
0x1e97  ret
0x1e98  ldnull
0x1e99  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e9e  ldc.i4.s 0x28
0x1ea0  ldstr    aSandboxhostsid_4// "SandboxHostSids.IsCallerAllowed: unexpe"...
0x1ea5  ldc.i4.1
0x1ea6  newarr   [mscorlib]System.Object
0x1eab  dup
0x1eac  ldc.i4.0
0x1ead  ldarg.2
0x1eae  ldind.ref
0x1eaf  stelem.ref
0x1eb0  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1eb5  ldc.i4.0
0x1eb6  ret
0x1eb7  ldloc.s  7
0x1eb9  ret
```
