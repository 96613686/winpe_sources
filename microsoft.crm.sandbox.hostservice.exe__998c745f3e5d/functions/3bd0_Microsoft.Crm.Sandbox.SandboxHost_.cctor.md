# Microsoft.Crm.Sandbox.SandboxHost::.cctor

- ea: `0x3bd0`
- end: `0x3cf3`
- name: `Microsoft.Crm.Sandbox.SandboxHost::.cctor`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x3bd0`
- `0x4e30`

## string_xrefs

- `0x3cda`: `SandboxHost: _serviceAccountSidSddlForm: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3bd0  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x3bd5  ldtoken  Microsoft.Crm.Sandbox.SandboxHost
0x3bda  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3bdf  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x3be4  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x3be9  stsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHost::Logger
0x3bee  ldc.i4.1
0x3bef  stsfld   valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxHost::_sandboxStatus
0x3bf4  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::.ctor()
0x3bf9  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::_hostConfiguration
0x3bfe  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::.ctor()
0x3c03  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxHost::_workerConfiguration
0x3c08  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x3c0d  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Sandbox.SandboxHost::_sandboxAdditionalInfo
0x3c12  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x3c17  stsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxHost::_shutdownTime
0x3c1c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>>::.ctor()
0x3c21  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>> Microsoft.Crm.Sandbox.SandboxHost::_workerExecutionRecordQueueDictionary
0x3c26  newobj   instance void [mscorlib]System.Object::.ctor()
0x3c2b  stsfld   object Microsoft.Crm.Sandbox.SandboxHost::_queueLock
0x3c30  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExponentialBackOff::.ctor()
0x3c35  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExponentialBackOff Microsoft.Crm.Sandbox.SandboxHost::_eventBackoff
0x3c3a  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter::.ctor()
0x3c3f  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter Microsoft.Crm.Sandbox.SandboxHost::_exceptionConverter
0x3c44  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0x3c49  stloc.0
0x3c4a  ldloc.0
0x3c4b  ldstr    aCurrentidentit// "currentIdentity"
0x3c50  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3c55  ldloc.0
0x3c56  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x3c5b  ldstr    aCurrentidentit_0// "currentIdentity.User"
0x3c60  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3c65  ldtoken  Microsoft.Crm.Sandbox.SandboxHost
0x3c6a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c6f  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x3c74  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x3c79  stloc.1
0x3c7a  ldloc.1
0x3c7b  brfalse.s loc_3C9A
0x3c7d  ldloc.1
0x3c7e  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x3c83  dup
0x3c84  callvirt instance int32 [System]System.Diagnostics.FileVersionInfo::get_FileMajorPart()
0x3c89  stsfld   int32 Microsoft.Crm.Sandbox.SandboxHost::_majorVersion
0x3c8e  callvirt instance int32 [System]System.Diagnostics.FileVersionInfo::get_FileMinorPart()
0x3c93  stsfld   int32 Microsoft.Crm.Sandbox.SandboxHost::_minorVersion
0x3c98  br.s     loc_3CA6
0x3c9a  ldc.i4.0
0x3c9b  stsfld   int32 Microsoft.Crm.Sandbox.SandboxHost::_majorVersion
0x3ca0  ldc.i4.0
0x3ca1  stsfld   int32 Microsoft.Crm.Sandbox.SandboxHost::_minorVersion
0x3ca6  ldloc.0
0x3ca7  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x3cac  ldc.i4.s 0x18
0x3cae  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x3cb3  call     void Microsoft.Crm.Sandbox.SandboxHost::set_IsNetworkServiceAccount(bool value)
0x3cb8  ldloc.0
0x3cb9  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x3cbe  ldstr    asc_1473C// ";"
0x3cc3  ldloc.0
0x3cc4  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x3cc9  call     string [mscorlib]System.String::Concat(object, object, object)
0x3cce  stsfld   string Microsoft.Crm.Sandbox.SandboxHost::_serviceAccountSidSddlForm
0x3cd3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3cd8  ldc.i4.s 0x26
0x3cda  ldstr    aSandboxhostSer// "SandboxHost: _serviceAccountSidSddlForm"...
0x3cdf  ldc.i4.1
0x3ce0  newarr   [mscorlib]System.Object
0x3ce5  dup
0x3ce6  ldc.i4.0
0x3ce7  ldsfld   string Microsoft.Crm.Sandbox.SandboxHost::_serviceAccountSidSddlForm
0x3cec  stelem.ref
0x3ced  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3cf2  ret
```
