# Microsoft.Xrm.Sdk.Client.ServiceProxy`1::Factory_Opened

- ea: `0x1bf20`
- end: `0x1bf31`
- name: `Microsoft.Xrm.Sdk.Client.ServiceProxy`1::Factory_Opened`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1aca0`

## string_xrefs

- `0x1bf21`: `The Factory has entered an opened state.`

## pseudocode

```c

```

## disassembly

```asm
0x1bf20  ldarg.0
0x1bf21  ldstr    aTheFactoryHasE_1// "The Factory has entered an opened state"...
0x1bf26  newobj   instance void Microsoft.Xrm.Sdk.Client.ChannelEventArgs::.ctor(string message)
0x1bf2b  callvirt instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::OnFactoryOpened(class Microsoft.Xrm.Sdk.Client.ChannelEventArgs)
0x1bf30  ret
```
