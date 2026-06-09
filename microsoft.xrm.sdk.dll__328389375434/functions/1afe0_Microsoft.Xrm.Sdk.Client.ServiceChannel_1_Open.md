# Microsoft.Xrm.Sdk.Client.ServiceChannel`1::Open

- ea: `0x1afe0`
- end: `0x1b023`
- name: `Microsoft.Xrm.Sdk.Client.ServiceChannel`1::Open`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1acf0`
- `0x1ad60`
- `0x1afe0`

## string_xrefs

- `0x1b003`: `Exception when opening an SDK channel`

## pseudocode

```c

```

## disassembly

```asm
0x1afe0  ldarg.0
0x1afe1  call     instance class [System.ServiceModel]System.ServiceModel.ICommunicationObject class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>>::get_CommunicationObject()
0x1afe6  brfalse.s loc_1B022
0x1afe8  ldarg.0
0x1afe9  call     instance class [System.ServiceModel]System.ServiceModel.ICommunicationObject class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>>::get_CommunicationObject()
0x1afee  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.ICommunicationObject::get_State()
0x1aff3  brtrue.s loc_1B022
0x1aff5  ldarg.0
0x1aff6  call     instance class [System.ServiceModel]System.ServiceModel.ICommunicationObject class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>>::get_CommunicationObject()
0x1affb  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Open()
0x1b000  leave.s  loc_1B022
0x1b002  stloc.0
0x1b003  ldstr    aExceptionWhenO// "Exception when opening an SDK channel"
0x1b008  ldloc.0
0x1b009  newobj   instance void Microsoft.Xrm.Sdk.Client.ChannelFaultedEventArgs::.ctor(string message, class [mscorlib]System.Exception exception)
0x1b00e  stloc.1
0x1b00f  ldarg.0
0x1b010  ldloc.1
0x1b011  callvirt instance void class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>>::OnChannelFaulted(class Microsoft.Xrm.Sdk.Client.ChannelFaultedEventArgs)
0x1b016  ldloc.1
0x1b017  callvirt instance bool Microsoft.Xrm.Sdk.Client.CancelEventArgs::get_Cancel()
0x1b01c  brtrue.s loc_1B020
0x1b01e  rethrow
0x1b020  leave.s  loc_1B022
0x1b022  ret
```
