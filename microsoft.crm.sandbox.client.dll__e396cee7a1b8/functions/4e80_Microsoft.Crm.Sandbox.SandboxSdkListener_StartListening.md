# Microsoft.Crm.Sandbox.SandboxSdkListener::StartListening

- ea: `0x4e80`
- end: `0x4f64`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::StartListening`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x30b0`
- `0x4d80`

## callees

- `0x38d0`
- `0x38e0`
- `0x4e80`
- `0x4f70`
- `0x5030`
- `0x5440`

## pseudocode

```c

```

## disassembly

```asm
0x4e80  call     bool Microsoft.Crm.Sandbox.SandboxSdkListener::get_ListenerStarted()
0x4e85  brfalse.s loc_4E88
0x4e87  ret
0x4e88  ldsfld   object Microsoft.Crm.Sandbox.SandboxSdkListener::_startListeningLock
0x4e8d  stloc.0
0x4e8e  ldc.i4.0
0x4e8f  stloc.1
0x4e90  ldloc.0
0x4e91  ldloca.s 1
0x4e93  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x4e98  call     bool Microsoft.Crm.Sandbox.SandboxSdkListener::get_ListenerStarted()
0x4e9d  brfalse.s loc_4EA4
0x4e9f  leave    loc_4F63
0x4ea4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ea9  ldc.i4.s 0x26
0x4eab  ldstr    aSandboxsdklist_15// "SandboxSdkListener.StartListening: _sta"...
0x4eb0  ldc.i4.1
0x4eb1  newarr   [mscorlib]System.Object
0x4eb6  dup
0x4eb7  ldc.i4.0
0x4eb8  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxSdkListener::_startListeningCount
0x4ebd  dup
0x4ebe  ldc.i4.1
0x4ebf  add
0x4ec0  stsfld   int32 Microsoft.Crm.Sandbox.SandboxSdkListener::_startListeningCount
0x4ec5  box      [mscorlib]System.Int32
0x4eca  stelem.ref
0x4ecb  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ed0  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxSdkListener::_listener
0x4ed5  brtrue.s loc_4EDE
0x4ed7  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxSdkListener::_anonymousClientListener
0x4edc  brfalse.s loc_4F15
0x4ede  ldnull
0x4edf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ee4  ldc.i4.s 0x26
0x4ee6  ldstr    aStartlistening// "StartListening: The SandboxListener is "...
0x4eeb  ldc.i4.2
0x4eec  newarr   [mscorlib]System.Object
0x4ef1  dup
0x4ef2  ldc.i4.0
0x4ef3  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxSdkListener::_startListeningCount
0x4ef8  box      [mscorlib]System.Int32
0x4efd  stelem.ref
0x4efe  dup
0x4eff  ldc.i4.1
0x4f00  call     bool Microsoft.Crm.Sandbox.SandboxSdkListener::get_ListenerStarted()
0x4f05  box      [mscorlib]System.Boolean
0x4f0a  stelem.ref
0x4f0b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4f10  call     void Microsoft.Crm.Sandbox.SandboxSdkListener::DisposeInnerListener()
0x4f15  call     void Microsoft.Crm.Sandbox.SandboxSdkListener::StartListenerWithAnonymousClient()
0x4f1a  call     void Microsoft.Crm.Sandbox.SandboxSdkListener::StartListenerWithWindowsAuth()
0x4f1f  ldc.i4.1
0x4f20  call     void Microsoft.Crm.Sandbox.SandboxSdkListener::set_ListenerStarted(bool value)
0x4f25  leave.s  loc_4F63
0x4f27  stloc.2
0x4f28  ldloc.2
0x4f29  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4f2e  ldc.i4.s 0x26
0x4f30  ldstr    aSdkListenerFai// "SDK Listener: failed to start: {0}, _st"...
0x4f35  ldc.i4.2
0x4f36  newarr   [mscorlib]System.Object
0x4f3b  dup
0x4f3c  ldc.i4.0
0x4f3d  ldloc.2
0x4f3e  stelem.ref
0x4f3f  dup
0x4f40  ldc.i4.1
0x4f41  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxSdkListener::_startListeningCount
0x4f46  box      [mscorlib]System.Int32
0x4f4b  stelem.ref
0x4f4c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4f51  ldc.i4.0
0x4f52  call     void Microsoft.Crm.Sandbox.SandboxSdkListener::set_ListenerStarted(bool value)
0x4f57  leave.s  loc_4F63
0x4f59  ldloc.1
0x4f5a  brfalse.s loc_4F62
0x4f5c  ldloc.0
0x4f5d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x4f62  endfinally
0x4f63  ret
```
