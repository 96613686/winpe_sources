# Microsoft.Xrm.Sdk.Client.ServiceChannel`1::Channel_Opened

- ea: `0x1b0d0`
- end: `0x1b0e1`
- name: `Microsoft.Xrm.Sdk.Client.ServiceChannel`1::Channel_Opened`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1aca0`

## string_xrefs

- `0x1b0d1`: `The channel has entered an opened state.`

## pseudocode

```c

```

## disassembly

```asm
0x1b0d0  ldarg.0
0x1b0d1  ldstr    aTheChannelHasE_1// "The channel has entered an opened state"...
0x1b0d6  newobj   instance void Microsoft.Xrm.Sdk.Client.ChannelEventArgs::.ctor(string message)
0x1b0db  callvirt instance void class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>>::OnChannelOpened(class Microsoft.Xrm.Sdk.Client.ChannelEventArgs)
0x1b0e0  ret
```
