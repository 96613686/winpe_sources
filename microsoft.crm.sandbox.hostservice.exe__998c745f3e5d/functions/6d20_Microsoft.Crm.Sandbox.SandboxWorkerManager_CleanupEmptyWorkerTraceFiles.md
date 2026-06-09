# Microsoft.Crm.Sandbox.SandboxWorkerManager::CleanupEmptyWorkerTraceFiles

- ea: `0x6d20`
- end: `0x6dde`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::CleanupEmptyWorkerTraceFiles`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4920`
- `0x6d20`
- `0x6de0`

## string_xrefs

- `0x6d4e`: `SandboxWorkerManager.CleanupEmptyWorkerTraceFiles: traceDirectory (local/registry): {0}`
- `0x6d8c`: `SandboxWorkerManager.CleanupEmptyWorkerTraceFiles: traceDirectory (remote/deployment): {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6d20  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d25  ldc.i4.s 0x21
0x6d27  ldstr    aSandboxworkerm_25// "SandboxWorkerManager.CleanupEmptyWorker"...
0x6d2c  ldc.i4.0
0x6d2d  newarr   [mscorlib]System.Object
0x6d32  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6d37  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_CrmServerInstallDirectory()
0x6d3c  ldstr    aTrace// "Trace"
0x6d41  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6d46  stloc.0
0x6d47  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d4c  ldc.i4.s 0x21
0x6d4e  ldstr    aSandboxworkerm_26// "SandboxWorkerManager.CleanupEmptyWorker"...
0x6d53  ldc.i4.1
0x6d54  newarr   [mscorlib]System.Object
0x6d59  dup
0x6d5a  ldc.i4.0
0x6d5b  ldloc.0
0x6d5c  stelem.ref
0x6d5d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6d62  ldloc.0
0x6d63  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::DeleteEmptyWorkerTraceFiles(string traceDirectory)
0x6d68  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxHost::get_RemoteTraceSettings()
0x6d6d  stloc.1
0x6d6e  ldloc.1
0x6d6f  brfalse.s loc_6DA6
0x6d71  ldloc.1
0x6d72  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings::get_TraceDirectory()
0x6d77  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6d7c  brtrue.s loc_6DA6
0x6d7e  ldloc.1
0x6d7f  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings::get_TraceDirectory()
0x6d84  stloc.0
0x6d85  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d8a  ldc.i4.s 0x21
0x6d8c  ldstr    aSandboxworkerm_27// "SandboxWorkerManager.CleanupEmptyWorker"...
0x6d91  ldc.i4.1
0x6d92  newarr   [mscorlib]System.Object
0x6d97  dup
0x6d98  ldc.i4.0
0x6d99  ldloc.0
0x6d9a  stelem.ref
0x6d9b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6da0  ldloc.0
0x6da1  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::DeleteEmptyWorkerTraceFiles(string traceDirectory)
0x6da6  leave.s  loc_6DC6
0x6da8  stloc.2
0x6da9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6dae  ldc.i4.s 0x21
0x6db0  ldstr    aSandboxworkerm_28// "SandboxWorkerManager.CleanupEmptyWorker"...
0x6db5  ldc.i4.1
0x6db6  newarr   [mscorlib]System.Object
0x6dbb  dup
0x6dbc  ldc.i4.0
0x6dbd  ldloc.2
0x6dbe  stelem.ref
0x6dbf  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6dc4  leave.s  loc_6DC6
0x6dc6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6dcb  ldc.i4.s 0x21
0x6dcd  ldstr    aSandboxworkerm_29// "SandboxWorkerManager.CleanupEmptyWorker"...
0x6dd2  ldc.i4.0
0x6dd3  newarr   [mscorlib]System.Object
0x6dd8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6ddd  ret
```
