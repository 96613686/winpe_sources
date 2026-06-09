# Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::get_Instance

- ea: `0x5620`
- end: `0x562b`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::get_Instance`
- size: `11`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3ca0`
- `0x4000`
- `0x4360`
- `0x4680`

## pseudocode

```c

```

## disassembly

```asm
0x5620  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource> Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::_instance
0x5625  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource>::get_Value()
0x562a  ret
```
