# Microsoft.Crm.Sandbox.HostServiceProgram::UnhandledExceptionHandler

- ea: `0xb40`
- end: `0xbf1`
- name: `Microsoft.Crm.Sandbox.HostServiceProgram::UnhandledExceptionHandler`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xb40`

## string_xrefs

- `0xbc1`: `MSCRMSandboxService`
- `0xb48`: `HostServiceProgram.UnhandledExceptionHandler: enter`

## pseudocode

```c

```

## disassembly

```asm
0xb40  ldnull
0xb41  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb46  ldc.i4.s 0x26
0xb48  ldstr    aHostservicepro// "HostServiceProgram.UnhandledExceptionHa"...
0xb4d  ldc.i4.0
0xb4e  newarr   [mscorlib]System.Object
0xb53  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb58  ldarg.1
0xb59  callvirt instance object [mscorlib]System.UnhandledExceptionEventArgs::get_ExceptionObject()
0xb5e  isinst   [mscorlib]System.Exception
0xb63  stloc.0
0xb64  ldloc.0
0xb65  brtrue.s loc_B68
0xb67  ret
0xb68  ldnull
0xb69  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb6e  ldc.i4.s 0x26
0xb70  ldstr    a0// "{0}"
0xb75  ldc.i4.1
0xb76  newarr   [mscorlib]System.Object
0xb7b  dup
0xb7c  ldc.i4.0
0xb7d  ldloc.0
0xb7e  stelem.ref
0xb7f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb84  ldstr    asc_F0E8// ""
0xb89  stloc.1
0xb8a  ldloc.0
0xb8b  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xb90  brfalse.s loc_B9E
0xb92  ldloc.0
0xb93  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xb98  callvirt instance string [mscorlib]System.Exception::get_Message()
0xb9d  stloc.1
0xb9e  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::get_Instance()
0xba3  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0xba8  ldloc.0
0xba9  callvirt instance string [mscorlib]System.Exception::get_Message()
0xbae  ldloc.1
0xbaf  ldloc.0
0xbb0  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0xbb5  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxHostUnhandledException(string, string, string, string)
0xbba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0xbbf  stloc.2
0xbc0  ldloc.2
0xbc1  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0xbc6  ldc.i4.1
0xbc7  ldc.i4   0xC0004F21
0xbcc  conv.u8
0xbcd  ldc.i4.2
0xbce  newarr   [mscorlib]System.Object
0xbd3  dup
0xbd4  ldc.i4.0
0xbd5  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0xbda  stelem.ref
0xbdb  dup
0xbdc  ldc.i4.1
0xbdd  ldloc.0
0xbde  stelem.ref
0xbdf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0xbe4  leave.s  loc_BF0
0xbe6  ldloc.2
0xbe7  brfalse.s loc_BEF
0xbe9  ldloc.2
0xbea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbef  endfinally
0xbf0  ret
```
