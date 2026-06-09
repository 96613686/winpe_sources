# Microsoft.Crm.Sandbox.SandboxSdkListener::DisposeInnerListener

- ea: `0x5440`
- end: `0x5475`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::DisposeInnerListener`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4e80`
- `0x50c0`

## callees

- `0x38d0`
- `0x5440`

## pseudocode

```c

```

## disassembly

```asm
0x5440  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxSdkListener::_listener
0x5445  brfalse.s loc_5451
0x5447  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxSdkListener::_listener
0x544c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5451  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxSdkListener::_anonymousClientListener
0x5456  brfalse.s loc_5462
0x5458  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxSdkListener::_anonymousClientListener
0x545d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5462  ldnull
0x5463  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxSdkListener::_listener
0x5468  ldnull
0x5469  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxSdkListener::_anonymousClientListener
0x546e  ldc.i4.0
0x546f  call     void Microsoft.Crm.Sandbox.SandboxSdkListener::set_ListenerStarted(bool value)
0x5474  ret
```
