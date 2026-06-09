# Microsoft.Crm.Sandbox.SandboxSdkListener::AuthenticateCaller

- ea: `0x5180`
- end: `0x536f`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::AuthenticateCaller`
- size: `495`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3ca0`
- `0x4000`
- `0x4360`
- `0x4680`

## callees

- `0xc0`
- `0x230`
- `0x1ec0`
- `0x4d00`
- `0x5180`
- `0x5370`

## string_xrefs

- `0x5236`: `SandboxSdkListener.AuthenticateCaller: SDK Listener: Access Denied`
- `0x530a`: `Access Denied. Reference number for administrators or support: #`
- `0x531f`: `SandboxSdkListener.AuthenticateCaller: {0} : Caller Information (Client/Host/Worker/Caller SID): {1} : Expected SID: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x5180  ldstr    aSandboxsdklist_19// "SandboxSdkListener.AuthenticateCaller"
0x5185  ldc.i4.3
0x5186  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x518b  stloc.0
0x518c  ldarg.1
0x518d  brfalse.s loc_5197
0x518f  ldarg.1
0x5190  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_OrganizationId()
0x5195  br.s     loc_519C
0x5197  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x519c  stloc.1
0x519d  ldloc.1
0x519e  ldc.i4.s 0x27
0x51a0  ldstr    aSandboxsdklist_20// "SandboxSdkListener.AuthenticateCaller: "...
0x51a5  ldc.i4.0
0x51a6  newarr   [mscorlib]System.Object
0x51ab  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x51b0  ldnull
0x51b1  stloc.2
0x51b2  ldstr    asc_C3B0// "-"
0x51b7  stloc.3
0x51b8  ldstr    asc_C3B0// "-"
0x51bd  stloc.s  4
0x51bf  ldarg.0
0x51c0  brfalse.s loc_5217
0x51c2  ldarg.0
0x51c3  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x51c8  brfalse.s loc_51EF
0x51ca  ldarg.0
0x51cb  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x51d0  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x51d5  brfalse.s loc_51EF
0x51d7  call     class Microsoft.Crm.Sandbox.SandboxCallManager Microsoft.Crm.Sandbox.SandboxCallManager::get_Instance()
0x51dc  ldarg.0
0x51dd  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x51e2  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x51e7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallManager::CheckCallTracker(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo sandboxCallInfo)
0x51ec  stloc.2
0x51ed  br.s     loc_5203
0x51ef  ldnull
0x51f0  ldloc.1
0x51f1  ldc.i4.s 0x21
0x51f3  ldstr    aSandboxsdklist_21// "SandboxSdkListener.AuthenticateCaller: "...
0x51f8  ldc.i4.0
0x51f9  newarr   [mscorlib]System.Object
0x51fe  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5203  ldloc.2
0x5204  brfalse.s loc_522C
0x5206  ldarg.2
0x5207  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x520c  brtrue.s loc_522C
0x520e  ldarg.2
0x520f  ldloc.2
0x5210  call     void Microsoft.Crm.Sandbox.SandboxSdkListener::ValidateValidRequest(string operationName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext pluginContext)
0x5215  br.s     loc_522C
0x5217  ldarg.1
0x5218  ldloca.s 3
0x521a  ldloca.s 4
0x521c  call     bool Microsoft.Crm.Sandbox.SandboxHostSids::IsCallerAllowed(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext requestContext, [out] string& expectedSidSddlForm, [out] string& callerSidSddlForm)
0x5221  brfalse.s loc_522C
0x5223  ldarg.1
0x5224  ldarg.2
0x5225  ldarg.2
0x5226  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxSdkListener::GetDefaultPluginContext(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext requestContext, string messageName, string requestName)
0x522b  stloc.2
0x522c  ldloc.2
0x522d  brtrue   loc_534A
0x5232  ldnull
0x5233  ldloc.1
0x5234  ldc.i4.s 0x21
0x5236  ldstr    aSandboxsdklist_22// "SandboxSdkListener.AuthenticateCaller: "...
0x523b  ldc.i4.0
0x523c  newarr   [mscorlib]System.Object
0x5241  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5246  ldstr    asc_C3B0// "-"
0x524b  stloc.s  5
0x524d  ldstr    asc_C3B0// "-"
0x5252  stloc.s  6
0x5254  ldstr    asc_C3B0// "-"
0x5259  stloc.s  7
0x525b  ldarg.0
0x525c  brfalse.s loc_529A
0x525e  ldarg.0
0x525f  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Summary()
0x5264  stloc.s  7
0x5266  ldarg.0
0x5267  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x526c  brfalse.s loc_529A
0x526e  ldarg.0
0x526f  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x5274  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Summary()
0x5279  stloc.s  6
0x527b  ldarg.0
0x527c  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x5281  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x5286  brfalse.s loc_529A
0x5288  ldarg.0
0x5289  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x528e  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x5293  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Summary()
0x5298  stloc.s  5
0x529a  ldc.i4.7
0x529b  newarr   [mscorlib]System.String
0x52a0  dup
0x52a1  ldc.i4.0
0x52a2  ldloc.s  5
0x52a4  stelem.ref
0x52a5  dup
0x52a6  ldc.i4.1
0x52a7  ldstr    asc_EA38// "/"
0x52ac  stelem.ref
0x52ad  dup
0x52ae  ldc.i4.2
0x52af  ldloc.s  6
0x52b1  stelem.ref
0x52b2  dup
0x52b3  ldc.i4.3
0x52b4  ldstr    asc_EA38// "/"
0x52b9  stelem.ref
0x52ba  dup
0x52bb  ldc.i4.4
0x52bc  ldloc.s  7
0x52be  stelem.ref
0x52bf  dup
0x52c0  ldc.i4.5
0x52c1  ldstr    asc_EA38// "/"
0x52c6  stelem.ref
0x52c7  dup
0x52c8  ldc.i4.6
0x52c9  ldloc.s  4
0x52cb  stelem.ref
0x52cc  call     string [mscorlib]System.String::Concat(string[])
0x52d1  stloc.s  8
0x52d3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x52d8  stloc.s  0xA
0x52da  ldloc.s  0xA
0x52dc  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0x52e1  ldc.i4.1
0x52e2  ldc.i4   0xC0004F06
0x52e7  conv.u8
0x52e8  ldc.i4.2
0x52e9  newarr   [mscorlib]System.Object
0x52ee  dup
0x52ef  ldc.i4.0
0x52f0  ldloc.s  8
0x52f2  stelem.ref
0x52f3  dup
0x52f4  ldc.i4.1
0x52f5  ldloc.3
0x52f6  stelem.ref
0x52f7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x52fc  leave.s  loc_530A
0x52fe  ldloc.s  0xA
0x5300  brfalse.s loc_5309
0x5302  ldloc.s  0xA
0x5304  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5309  endfinally
0x530a  ldstr    aAccessDeniedRe// "Access Denied. Reference number for adm"...
0x530f  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ReferenceId()
0x5314  call     string [mscorlib]System.String::Concat(string, string)
0x5319  stloc.s  9
0x531b  ldnull
0x531c  ldloc.1
0x531d  ldc.i4.s 0x21
0x531f  ldstr    aSandboxsdklist_23// "SandboxSdkListener.AuthenticateCaller: "...
0x5324  ldc.i4.3
0x5325  newarr   [mscorlib]System.Object
0x532a  dup
0x532b  ldc.i4.0
0x532c  ldloc.s  9
0x532e  stelem.ref
0x532f  dup
0x5330  ldc.i4.1
0x5331  ldloc.s  8
0x5333  stelem.ref
0x5334  dup
0x5335  ldc.i4.2
0x5336  ldloc.3
0x5337  stelem.ref
0x5338  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x533d  ldloc.s  9
0x533f  ldc.i4   0x80048405
0x5344  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5349  throw
0x534a  ldloc.1
0x534b  ldc.i4.s 0x27
0x534d  ldstr    aSandboxsdklist_24// "SandboxSdkListener.AuthenticateCaller: "...
0x5352  ldc.i4.0
0x5353  newarr   [mscorlib]System.Object
0x5358  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x535d  ldloc.2
0x535e  stloc.s  0xB
0x5360  leave.s  loc_536C
0x5362  ldloc.0
0x5363  brfalse.s loc_536B
0x5365  ldloc.0
0x5366  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x536b  endfinally
0x536c  ldloc.s  0xB
0x536e  ret
```
