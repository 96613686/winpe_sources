# Microsoft.Crm.Sandbox.SandboxSdkListener::SdkListenerStarterThread

- ea: `0x4d80`
- end: `0x4e5e`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::SdkListenerStarterThread`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x38e0`
- `0x3900`
- `0x4d80`
- `0x4e80`

## string_xrefs

- `0x4d87`: `SandboxSdkListener.SdkListenerStarterThread: enter`
- `0x4db2`: `SandboxSdkListener.SdkListenerStarterThread: exit/success`
- `0x4de8`: `SandboxSdkListener.SdkListenerStarterThread: _starterThreadEvent signaled/timed out`
- `0x4e0c`: `SandboxSdkListener.SdkListenerStarterThread: exit/shutdown`
- `0x4e41`: `SandboxSdkListener.SdkListenerStarterThread: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4d80  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4d85  ldc.i4.s 0x21
0x4d87  ldstr    aSandboxsdklist_10// "SandboxSdkListener.SdkListenerStarterTh"...
0x4d8c  ldc.i4.0
0x4d8d  newarr   [mscorlib]System.Object
0x4d92  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4d97  ldc.i4.1
0x4d98  stsfld   bool Microsoft.Crm.Sandbox.SandboxSdkListener::_starterThreadRunning
0x4d9d  ldc.i4.1
0x4d9e  stloc.0
0x4d9f  call     void Microsoft.Crm.Sandbox.SandboxSdkListener::StartListening()
0x4da4  call     bool Microsoft.Crm.Sandbox.SandboxSdkListener::get_ListenerStarted()
0x4da9  brfalse.s loc_4DCD
0x4dab  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4db0  ldc.i4.s 0x21
0x4db2  ldstr    aSandboxsdklist_11// "SandboxSdkListener.SdkListenerStarterTh"...
0x4db7  ldc.i4.0
0x4db8  newarr   [mscorlib]System.Object
0x4dbd  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4dc2  ldc.i4.0
0x4dc3  stsfld   bool Microsoft.Crm.Sandbox.SandboxSdkListener::_starterThreadRunning
0x4dc8  leave    loc_4E5D
0x4dcd  ldsfld   class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Sandbox.SandboxSdkListener::_starterThreadEvent
0x4dd2  ldc.i4.0
0x4dd3  ldc.i4.0
0x4dd4  ldloc.0
0x4dd5  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x4dda  ldc.i4.0
0x4ddb  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan, bool)
0x4de0  pop
0x4de1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4de6  ldc.i4.s 0x21
0x4de8  ldstr    aSandboxsdklist_12// "SandboxSdkListener.SdkListenerStarterTh"...
0x4ded  ldc.i4.0
0x4dee  newarr   [mscorlib]System.Object
0x4df3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4df8  call     bool Microsoft.Crm.Sandbox.SandboxSdkListener::get_IsShutdown()
0x4dfd  brfalse.s loc_4E1E
0x4dff  ldc.i4.0
0x4e00  stsfld   bool Microsoft.Crm.Sandbox.SandboxSdkListener::_starterThreadRunning
0x4e05  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4e0a  ldc.i4.s 0x21
0x4e0c  ldstr    aSandboxsdklist_13// "SandboxSdkListener.SdkListenerStarterTh"...
0x4e11  ldc.i4.0
0x4e12  newarr   [mscorlib]System.Object
0x4e17  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e1c  leave.s  loc_4E5D
0x4e1e  ldloc.0
0x4e1f  ldc.i4.s 0x3C
0x4e21  bge      loc_4D9F
0x4e26  ldloc.0
0x4e27  ldc.i4.2
0x4e28  mul
0x4e29  stloc.0
0x4e2a  ldloc.0
0x4e2b  ldc.i4.s 0x3C
0x4e2d  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x4e32  stloc.0
0x4e33  br       loc_4D9F
0x4e38  stloc.1
0x4e39  ldloc.1
0x4e3a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4e3f  ldc.i4.s 0x26
0x4e41  ldstr    aSandboxsdklist_14// "SandboxSdkListener.SdkListenerStarterTh"...
0x4e46  ldc.i4.1
0x4e47  newarr   [mscorlib]System.Object
0x4e4c  dup
0x4e4d  ldc.i4.0
0x4e4e  ldloc.1
0x4e4f  stelem.ref
0x4e50  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4e55  ldc.i4.0
0x4e56  stsfld   bool Microsoft.Crm.Sandbox.SandboxSdkListener::_starterThreadRunning
0x4e5b  rethrow
0x4e5d  ret
```
