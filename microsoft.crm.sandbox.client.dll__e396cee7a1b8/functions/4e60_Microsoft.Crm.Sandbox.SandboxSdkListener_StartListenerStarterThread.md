# Microsoft.Crm.Sandbox.SandboxSdkListener::StartListenerStarterThread

- ea: `0x4e60`
- end: `0x4e78`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::StartListenerStarterThread`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xed0`

## pseudocode

```c

```

## disassembly

```asm
0x4e60  ldnull
0x4e61  ldftn    void Microsoft.Crm.Sandbox.SandboxSdkListener::SdkListenerStarterThread(object info)
0x4e67  newobj   instance void [mscorlib]System.Threading.ParameterizedThreadStart::.ctor(object, native int)
0x4e6c  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ParameterizedThreadStart)
0x4e71  ldnull
0x4e72  callvirt instance void [mscorlib]System.Threading.Thread::Start(object)
0x4e77  ret
```
